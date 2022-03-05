<template>
  <h1>Job Details Page</h1>
  <p>The job id is: {{ id }}</p>
</template>

<script>
export default {
  name: "JobsDetails",
  props: ["id"],
};
</script>
