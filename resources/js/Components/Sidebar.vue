<template>
  <ul class="c-sidebar-nav">
    <li class="c-sidebar-nav-item">
      <Link
        class="c-sidebar-nav-link"
        v-if="hasAnyPermission(['dashboard.index'])"
        :class="{ active: $page.url.startsWith('/apps/dashboard') }"
        href="/apps/dashboard"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-speedometer2"
          viewBox="0 0 16 16"
        >
          <path
            d="M8 4a.5.5 0 0 1 .5.5V6a.5.5 0 0 1-1 0V4.5A.5.5 0 0 1 8 4zM3.732 5.732a.5.5 0 0 1 .707 0l.915.914a.5.5 0 1 1-.708.708l-.914-.915a.5.5 0 0 1 0-.707zM2 10a.5.5 0 0 1 .5-.5h1.586a.5.5 0 0 1 0 1H2.5A.5.5 0 0 1 2 10zm9.5 0a.5.5 0 0 1 .5-.5h1.5a.5.5 0 0 1 0 1H12a.5.5 0 0 1-.5-.5zm.754-4.246a.389.389 0 0 0-.527-.02L7.547 9.31a.91.91 0 1 0 1.302 1.258l3.434-4.297a.389.389 0 0 0-.029-.518z"
          />
          <path
            fill-rule="evenodd"
            d="M0 10a8 8 0 1 1 15.547 2.661c-.442 1.253-1.845 1.602-2.932 1.25C11.309 13.488 9.475 13 8 13c-1.474 0-3.31.488-4.615.911-1.087.352-2.49.003-2.932-1.25A7.988 7.988 0 0 1 0 10zm8-7a7 7 0 0 0-6.603 9.329c.203.575.923.876 1.68.63C4.397 12.533 6.358 12 8 12s3.604.532 4.923.96c.757.245 1.477-.056 1.68-.631A7 7 0 0 0 8 3z"
          />
        </svg>
        <span class="ms-2">Dashboard</span>
      </Link>
    </li>

    <li
      class="c-sidebar-nav-title"
      v-if="
        hasAnyPermission(['categories.index']) ||
        hasAnyPermission(['products.index'])
      "
    >
      MASTER
    </li>

    <li
      class="c-sidebar-nav-item"
      v-if="hasAnyPermission(['categories.index'])"
    >
      <Link
        class="c-sidebar-nav-link"
        href="/apps/categories"
        :class="{ active: $page.url.startsWith('/apps/categories') }"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-folder"
          viewBox="0 0 16 16"
        >
          <path
            d="M.54 3.87.5 3a2 2 0 0 1 2-2h3.672a2 2 0 0 1 1.414.586l.828.828A2 2 0 0 0 9.828 3h3.982a2 2 0 0 1 1.992 2.181l-.637 7A2 2 0 0 1 13.174 14H2.826a2 2 0 0 1-1.991-1.819l-.637-7a1.99 1.99 0 0 1 .342-1.31zM2.19 4a1 1 0 0 0-.996 1.09l.637 7a1 1 0 0 0 .995.91h10.348a1 1 0 0 0 .995-.91l.637-7A1 1 0 0 0 13.81 4H2.19zm4.69-1.707A1 1 0 0 0 6.172 2H2.5a1 1 0 0 0-1 .981l.006.139C1.72 3.042 1.95 3 2.19 3h5.396l-.707-.707z"
          />
        </svg>
        <span class="ms-2">Categories</span>
      </Link>
    </li>

    <li class="c-sidebar-nav-item" v-if="hasAnyPermission(['products.index'])">
      <Link
        class="c-sidebar-nav-link"
        href="/apps/products"
        :class="{ active: $page.url.startsWith('/apps/products') }"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-bag"
          viewBox="0 0 16 16"
        >
          <path
            d="M8 1a2.5 2.5 0 0 1 2.5 2.5V4h-5v-.5A2.5 2.5 0 0 1 8 1zm3.5 3v-.5a3.5 3.5 0 1 0-7 0V4H1v10a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V4h-3.5zM2 5h12v9a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V5z"
          />
        </svg>
        <span class="ms-2">Products</span>
      </Link>
    </li>

    <li class="c-sidebar-nav-item" v-if="hasAnyPermission(['customers.index'])">
      <Link
        class="c-sidebar-nav-link"
        href="/apps/customers"
        :class="{ active: $page.url.startsWith('/apps/customers') }"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-person-circle"
          viewBox="0 0 16 16"
        >
          <path d="M11 6a3 3 0 1 1-6 0 3 3 0 0 1 6 0z" />
          <path
            fill-rule="evenodd"
            d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8zm8-7a7 7 0 0 0-5.468 11.37C3.242 11.226 4.805 10 8 10s4.757 1.225 5.468 2.37A7 7 0 0 0 8 1z"
          />
        </svg>
        <span class="ms-2">Customers</span>
      </Link>
    </li>

    <li
      class="c-sidebar-nav-title"
      v-if="hasAnyPermission(['transactions.index'])"
    >
      TRANSACTIONS
    </li>

    <li
      class="c-sidebar-nav-item"
      v-if="hasAnyPermission(['transactions.index'])"
    >
      <Link
        class="c-sidebar-nav-link"
        href="/apps/transactions"
        :class="{ active: $page.url.startsWith('/apps/transactions') }"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-cart"
          viewBox="0 0 16 16"
        >
          <path
            d="M0 1.5A.5.5 0 0 1 .5 1H2a.5.5 0 0 1 .485.379L2.89 3H14.5a.5.5 0 0 1 .491.592l-1.5 8A.5.5 0 0 1 13 12H4a.5.5 0 0 1-.491-.408L2.01 3.607 1.61 2H.5a.5.5 0 0 1-.5-.5zM3.102 4l1.313 7h8.17l1.313-7H3.102zM5 12a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm7 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm-7 1a1 1 0 1 1 0 2 1 1 0 0 1 0-2zm7 0a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"
          />
        </svg>
        <span class="ms-2">Transactions</span>
      </Link>
    </li>

    <li
      class="c-sidebar-nav-title"
      v-if="
        hasAnyPermission(['sales.index']) || hasAnyPermission(['profits.index'])
      "
    >
      REPORTS
    </li>

    <li class="c-sidebar-nav-item" v-if="hasAnyPermission(['sales.index'])">
      <Link
        class="c-sidebar-nav-link"
        href="/apps/sales"
        :class="{ active: $page.url.startsWith('/apps/sales') }"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-bar-chart"
          viewBox="0 0 16 16"
        >
          <path
            d="M4 11H2v3h2v-3zm5-4H7v7h2V7zm5-5v12h-2V2h2zm-2-1a1 1 0 0 0-1 1v12a1 1 0 0 0 1 1h2a1 1 0 0 0 1-1V2a1 1 0 0 0-1-1h-2zM6 7a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v7a1 1 0 0 1-1 1H7a1 1 0 0 1-1-1V7zm-5 4a1 1 0 0 1 1-1h2a1 1 0 0 1 1 1v3a1 1 0 0 1-1 1H2a1 1 0 0 1-1-1v-3z"
          />
        </svg>
        <span class="ms-2">Report Sales</span>
      </Link>
    </li>
    <li class="c-sidebar-nav-item" v-if="hasAnyPermission(['profits.index'])">
      <Link
        class="c-sidebar-nav-link"
        href="/apps/profits"
        :class="{ active: $page.url.startsWith('/apps/profits') }"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="bi bi-graph-up-arrow"
          viewBox="0 0 16 16"
        >
          <path
            fill-rule="evenodd"
            d="M0 0h1v15h15v1H0V0Zm10 3.5a.5.5 0 0 1 .5-.5h4a.5.5 0 0 1 .5.5v4a.5.5 0 0 1-1 0V4.9l-3.613 4.417a.5.5 0 0 1-.74.037L7.06 6.767l-3.656 5.027a.5.5 0 0 1-.808-.588l4-5.5a.5.5 0 0 1 .758-.06l2.609 2.61L13.445 4H10.5a.5.5 0 0 1-.5-.5Z"
          />
        </svg>
        <span class="ms-2">Report Profits</span>
      </Link>
    </li>

    

    <li class="c-sidebar-nav-divider"></li>
  </ul>
</template>

<script>
//import Link
import { Link } from "@inertiajs/inertia-vue3";

export default {
  components: {
    Link,
  },
};
</script>

<style>
</style>