<template>
  <transition name="page">
    <router-view />
  </transition>
</template>

<static-query>
query {
 metadata {
     siteName,
     siteDescription
 }
}
</static-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$static.metadata.siteName,
      meta: [
        {
          key: "description",
          name: "description",
          content: this.$static.metadata.siteDescription
        }
      ]
    };
  }
};
</script>