<!-- BadgeEmbed.vue -->
<template>
    <div>
      <div
        data-iframe-width="150"
        data-iframe-height="270"
        data-share-badge-id="2cdd1f95-d6ad-492f-85dd-d2e643f4d044"
        data-share-badge-host="https://www.credly.com"
      ></div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'BadgeEmbed',
    mounted() {
      // Embed the script dynamically
      const script = document.createElement('script');
      script.type = 'text/javascript';
      script.async = true;
      script.src = '//cdn.credly.com/assets/utilities/embed.js';
  
      // Append the script to the body or another appropriate container
      document.body.appendChild(script);
    },
  };
  </script>
  
  <style scoped>
  /* Add any necessary styles for your component */
  </style>
  