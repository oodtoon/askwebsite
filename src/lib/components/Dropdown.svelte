<script lang="ts"></script>

<div class="dropdown">
  <slot/>
</div>

<style>

  .dropdown {
    position: absolute;
    color: white;
    background-color: var(--ask-purple);
    top: 7em;
    padding: 1em;
    box-shadow: var(--ask-shadow);
  }
</style>