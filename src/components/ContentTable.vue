<template>
  <table class="table table-striped">
    <thead>
      <tr>
        <th scope="col"></th>
        <th scope="col">Name</th>
        <!-- <th scope="col">Created by</th> -->
        <th scope="col">Updated at</th>
        <th scope="col">Updated by</th>
        <th scope="col">Size</th>
        <th scope="col">Created at</th>
      </tr>
    </thead>
    <tbody>
      <template v-for="(content, index) in contents">
        <tr :key="`content_${index}`">
          <th scope="row">🗂</th>
          <td>
            Mark
          </td>
          <td>Otto</td>
          <!-- <td>@mdo</td> -->
          <td>@mdo</td>
          <td>@mdo</td>
          <td>@mdo</td>
        </tr>
      </template>
    </tbody>
  </table>
</template>
<script>
export default {
  data () {
    return {
      contents: [
        {},
        {},
        {},
      ]
    };
  },
  created () {
    this.getContents();
  },
  getContents () {
    axios.get('').then((response) => {
      console.error(response)
    }).catch((error) => {
    });
  }
}
</script>