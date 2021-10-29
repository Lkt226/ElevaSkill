<template>
  <NuxtLink id="jobs" :to="path">
      <span class="span">
          <h3>
              {{ title }}
          </h3>
          <p>
              {{ date }}
          </p>
      </span>
      <Divider/>
      <h4>{{company}} | {{seniority}}</h4>
  </NuxtLink>
</template>

<script>
export default {
    props: {
        title: String,
        date: String,
        company: String,
        seniority: String,
        path: String
    }
}
</script>

<style scoped>
    #jobs{
        width: calc(100% - 1.5rem);
    }
    .span {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;

        width: 100%;
    }
</style>