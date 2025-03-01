<script>
export default {
  props: {
    type: {
      type: String,
      default: 'info',
      validator(value) {
        return ['info', 'success', 'warning', 'danger'].includes(value)
      },
    },
  },
}
</script>

<template>
  <div :class="[$style.alert, $style[type]]" role="alert">
    <slot></slot>
  </div>
</template>

<style module>
.alert {
  background-color: hsl(0, 0, 95%);
  border-color: rgb(0, 110, 255);
  @apply border-l-8;
  @apply p-5;
  @apply mb-5;

  @apply border-l-4;
  @apply border-gray-600;
  @apply px-12;
  @apply py-6;
  @apply mb-8;
}

.alert > :last-child {
  @apply mb-0;
}

/* #region info */

.info {
  border-left-color: #2a98b9;
  background-color: #f2fafd;
}

.info :global(.alert-header) {
  color: #2a98b9;
}

.info a {
  color: #2a98b9;
  border-bottom-color: #2a98b9;
}

.info a > code {
  color: #2a98b9;
}

/* #endregion info */

h2 {
  @apply text-xl;
}

.alert :global(h1.alert-header) {
  @apply block;
  @apply text-lg;
  @apply font-medium;
}

.alert h2,
.alert h3,
.alert h4,
.alert h5 {
  @apply text-xl;
  @apply flex;
  @apply flex-row;
  @apply items-center;
  @apply font-bold;
  @apply mb-4;
}

.alert h2,
.alert h3,
.alert h4,
.alert h5 .badge {
  @apply ml-2;
}

.alert h2 > svg,
.alert h3 > svg,
.alert h4 > svg,
.alert h5 > svg {
  @apply h-7;
  @apply w-7;
  @apply mr-2;
}

.alert ul {
  @apply list-disc;
}

.alert li {
  @apply font-normal;
  @apply mt-4;
  @apply mb-4;
}

.alert > code {
  background-color: rgb(220, 241, 247);
}

/* #region inside-code-block-component */

:global(.code-block) .alert {
  @apply px-6;
  @apply py-4;
  @apply mb-0;
}

:global(.code-block) .alert p {
  @apply text-sm;
}

/* #endregion inside-code-block-component */

/* #region success */

.success {
  border-left-color: #00bf88;
  background-color: rgb(241, 253, 249);
}

.success :global(.alert-header) {
  color: #00bf88;
}

.success a {
  color: #00bf88;
  border-bottom-color: #00bf88;
}

.success > code {
  background-color: rgb(207, 241, 230);
}

.success a > code {
  color: #00bf88;
}

/* #endregion success */

/* #region warning */

.warning {
  border-left-color: rgb(240, 173, 78);
  background-color: rgb(255, 251, 245);
}

.warning :global(.alert-header) {
  color: rgb(240, 173, 78);
}

.warning a {
  color: rgb(240, 173, 78);
  border-bottom-color: rgb(240, 173, 78);
}

.warning > code {
  background-color: rgb(247, 235, 215);
}

.warning a > code {
  color: rgb(240, 173, 78);
}

/* #endregion warning */

/* #region danger */

.danger {
  border-left-color: rgb(217, 83, 79);
  background-color: rgb(255, 242, 242);
}

.danger :global(.alert-header) {
  color: rgb(222, 94, 90);
}

.danger a {
  color: rgb(222, 94, 90);
  border-bottom-color: rgb(222, 94, 90);
}

.danger > code {
  background-color: rgb(245, 228, 228);
}

.danger a > code {
  color: rgb(222, 94, 90);
}

/* #endregion danger */
</style>
