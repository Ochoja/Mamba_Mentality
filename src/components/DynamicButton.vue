<script></script>

<template>
  <button>
    <slot>Click Me!</slot>
  </button>
</template>

<style>
button {
  background: var(--secondary-color);
  color: #000;
  border-radius: 4px;
  padding: 9px 16px;
  border: none;
  font-weight: 700;
}
</style>
