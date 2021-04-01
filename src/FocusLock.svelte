<script context="module">
  import {lock} from "./FocusLock";

  /**
   * Usage: <div use:portal={'css selector'}> or <div use:portal={document.body}>
   *
   * @param {HTMLElement} el
   */
  export function focusLock(el) {
    function destroy() {
      if (el.parentNode) {
        el.parentNode.removeChild(el);
      }
    }

    lock(el);
    return {
      lock,
      destroy,
    };
  }
</script>
