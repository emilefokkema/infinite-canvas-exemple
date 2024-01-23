<script lang="ts">
  import { onMount } from "svelte";
  import InfiniteCanvas, {
    type InfiniteCanvasRenderingContext2D,
  } from "ef-infinite-canvas";

  export let width: number;
  export let height: number;

  let canvas: HTMLCanvasElement;
  let context: InfiniteCanvasRenderingContext2D | null;

  const draw = () => {
    if (context && canvas) {

      const res = 21;
      let imageData = new ImageData(100, 100);

      context.putImageData(
        imageData,
        0, 0
      );
    }
  };

  onMount(() => {
    if (!canvas) return;
    const infinite_canvas = new InfiniteCanvas(canvas);
    infinite_canvas.greedyGestureHandling = true;
    context = infinite_canvas.getContext("2d");
    if (!context) return;
    draw();
  });

  
</script>

<canvas
  bind:this={canvas}
  {width}
  {height}
  style="width: {width}px; height: {height}px; background-color: #709c8d;"
/>
