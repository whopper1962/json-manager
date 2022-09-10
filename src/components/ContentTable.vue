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
            <router-link
              :to="{
                name: 'Details',
                params: {
                  content_id: content.id
                }
              }"
            >
              Mark
            </router-link>
          </td>
          <td>
            {{ content.updated_at }}
          </td>
          <!-- <td>@mdo</td> -->
          <td>
            {{ content.updated_by }}
          </td>
          <td>
            <template v-if="content.content_type === 'folder'">
              {{ content.content_size }} Files
            </template>
            <template v-else>
              {{ content.content_size }} MB
            </template>
          </td>
          <td>
            {{ content.created_at }}
          </td>
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
        {
          id: 1,
          content_type: 'folder',
          content_size: '10',
          updated_at: '2022/10/15 10:25',
          updated_by: 'Masashi Kawakami',
          created_at: '2022/8/26 12:35'
        },
        {
          id: 2,
          content_type: 'file',
          content_size: '10',
          updated_at: '2022/10/15 10:25',
          updated_by: 'Masashi Kawakami',
          created_at: '2022/8/26 12:35'
        },
        {
          id: 3,
          content_type: 'folder',
          content_size: '10',
          updated_at: '2022/10/15 10:25',
          updated_by: 'Masashi Kawakami',
          created_at: '2022/8/26 12:35'
        },
      ]
    };
  },
  created () {
    // this.getContents();
  },
  getContents () {
    axios.get('').then((response) => {
      console.error(response)
    }).catch((error) => {
    });
  }
}
</script>