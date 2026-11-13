# Example blueprints

Each file is a complete OpenAPPL blueprint. Only the choices that matter for the example
are written; every other property takes its documented default. All three validate with
no errors against the reference compiler for the schema version of this repository.

The one informational warning each of them reports
(`TOPIC_NO_CONSUMER` on `...-auth-service-user-logged-in`) comes from the authentication
service that every project with an `authentication` section gets: it announces logins,
and these examples do not consume the announcement.

## `todo.json`: a private task list

- One service, `tasks`, with one data object, `task`.
- `ownerId` is a **session-bound owner field** (`sessionSettings.isOwnerField`): it is
  filled from the caller's session and decides who owns a row.
- Four business APIs, one per basic type: `createTask`, `listTasks`, `updateTask`,
  `deleteTask`. The last three set `ownershipCheck`, so a user only ever sees and changes
  their own tasks.
- The `authentication` section switches on sign-up and login; the compiler adds the
  whole authentication service from it.

## `blog.json`: posts and comments

- Two data objects in one service: `post` and `comment`, related through
  `comment.postId`; deleting a post deletes its comments (`onDeleteAction: doDelete`).
- `post.status` is an **enum** (`draft`, `published`) with a default.
- `listPublishedPosts` and `getPost` are **public** (`loginRequired: false`) and only ever
  return published posts, through a where clause written in MScript:
  `{ status: 'published' }`.
- `publishPost` is an update that only the author can run, and it sets the status and the
  publication date in its data clause.

## `shop.json`: a checkout order

- `product` is a public catalogue; `order` is private to the customer who placed it.
- `order` sets `objectSettings.checkout.objectIsAnOrderObject` and maps its own
  properties (amount, currency, status, owner) onto the checkout. This is a
  **high-level pattern**: the compiler lowers it into
  - the system data objects `sys_orderPayment`, `sys_orderRefund`, `sys_orderDispute`,
    `sys_paymentEvent` and `sys_paymentWebhookSecret` in the `sales` service, and
    `sys_paymentCustomer` and `sys_paymentMethod` in the authentication service,
  - the business APIs `getOrderPayment`, `listOrderPayments`, `createOrderPayment`,
    `updateOrderPayment`, `deleteOrderPayment`, `getOrderPaymentByOrderId`,
    `getOrderPaymentByPaymentId`, `listPaymentEvents` and `getPaymentEvent`,
  - the payment routes (start, refresh and complete a payment, refund, provider webhook).

  None of these appear in the blueprint. Part 3, chapter 12 of the specification lists
  what every high-level pattern lowers to.
- `mapPaymentResultToOrderStatus` says which order status each payment result writes.
- The payment provider's keys are **environment references** (`$ENV:STRIPE_SECRET_KEY`),
  never literal secrets. Set the variables in the environment the generated services run
  in.
