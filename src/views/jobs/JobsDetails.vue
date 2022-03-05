<template>
  <div v-if="job">
    <h1>{{ job.title }}</h1>
    <p>{{ job.details }}</p>
  </div>
  <div v-else>
    <p>Loading data...</p>
  </div>
</template>

<script>
export default {
  name: "JobsDetails",
  props: ["id"],
  data() {
    return {
      job: null,
    };
  },
  mounted() {
    const jobId = this.id;
    fetch(`http://localhost:3000/jobs/${jobId}`)
      .then((response) => response.json())
      .then((data) => (this.job = data))
      .catch((error) => console.log(error));
  },
};
</script>
