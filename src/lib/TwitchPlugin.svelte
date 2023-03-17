<script context="module" lang="ts">
    export let channel = "divancetwitch";
</script>
  
  <div
    class="twitch-embed"
    use:embedTwitch={channel}
    style="width: 100%; height: 100%;"
  ></div>
  
<script>
    function embedTwitch(node, channel) {
      const script = document.createElement("script");
      script.src = "https://embed.twitch.tv/embed/v1.js";
      script.onload = () => {
        new Twitch.Embed(node, {
          width: "100%",
          height: "100%",
          channel: channel,
          theme: "dark",
          autoplay: false,
        });
      };
      document.head.appendChild(script);
  
      return {
        destroy() {
          document.head.removeChild(script);
        },
      };
    }
</script>
  
<style>
  .twitch-embed {
    border: 3px solid #ccc;
  }
</style>
