<script>
  import Window from "./components/Window.svelte";

  // Handle responsive iframes for embeds
  import pym from "pym.js";

  new pym.Child({
    polling: 500,
  });
</script>

<Window />
<!-- Outer div must have class 'chart-container' don't change -->
<div class="chart-container">
  <h1 class="headline">
    Trends in annual water-quality loads to the Gulf of Mexico
  </h1>
  <p class="dek">
    The Mississippi River/Gulf of Mexico Hypoxia Task Force uses two metrics to
    assess progress toward its reduction targets. Flow-normalization removes
    weather-driven variability to highlight long-term changes due to factors
    like nutrient runoff, while the 5-year rolling average shows a smoother view
    of actual computed constituent loads.

    <br /><br />
    <span style="display: flex; align-items: center; gap: 4px;">
      <span style="display: flex; align-items: center; gap: 0px;">
        <span
          style="width: 15px; height: 3px; display: inline-block; background: #6da34d; "
        ></span>
        <span
          style="width: 10px; height: 10px; border-radius: 50%; display: inline-block; border: 3px solid #6da34d; "
        ></span>
      </span>Flow-normalized water-quality loads &nbsp;&nbsp;&nbsp;

      <span style="display: flex; align-items: center; gap: 0px;">
        <span
          style="width: 15px; height: 3px; display: inline-block; background: #f1b82d; "
        ></span>
        <span
          style="width: 10px; height: 10px; border-radius: 50%; display: inline-block; border: 3px solid #f1b82d; "
        ></span>
      </span>5-year rolling average
    </span>
  </p>
  <p class="sr-only">[altText]</p>

  <div class="flex">
    <div class="box">
      <h2>Nitrate</h2>
      <span>In tons</span>
      <img src="nitrate.png" />
    </div>

    <div class="box">
      <h2>Phosphorus</h2>
      <span>In tons</span>
      <img src="phosphorus.png" />
    </div>
  </div>
</div>

<style lang="scss">
  .chart-container {
    max-width: 800px;
    width: 100%;
    padding: 0.5rem;

    .flex {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;

      @include mq(500px, "min-width") {
        flex-wrap: nowrap;
      }

      .box {
        overflow-y: hidden;
        aspect-ratio: 1 / 0.99;

        h2 {
          font-weight: bold;
        }

        span {
          font-size: 0.9rem;
          font-style: italic;
          color: #666;
        }
      }
    }
  }

  .g-span {
    &.g-with {
      color: #6da34d;
    }
    &.g-without {
      color: #f1b82d;
    }
  }
</style>
