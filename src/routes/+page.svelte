<script>
  import TestComponent from "./TestComponent.svelte";

  let screenWidth;
  let screenHeight;
</script>

<div
  class="bg-blue-800 w-full h-screen"
  bind:clientWidth={screenWidth}
  bind:clientHeight={screenHeight}
>
  <TestComponent width={screenWidth} height={screenHeight} />
</div>
