<style lang=less>
  img {
    width: 20px;
  }
</style>

<template>
  <form class="ui form">
    <div class="inline fields">
      <div class="eight wide field">
        <label>Name</label>
        <input type="text" placeholder="First Name">
      </div>
      <div class="eight wide field">
        <div class="ui right floated primary button" ><i class="search icon"></i>搜索</div>
        <div class="ui right floated button"><i class="repeat icon"></i>重置</div>
      </div>
    </div>
  </form>
  <table class="ui celled table">
      <thead>
        <tr><th>Header</th>
          <th>Header</th>
          <th>Header</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Cell</td>
          <td>Cell</td>
          <td>Cell</td>
        </tr>
        <tr>
          <td>Cell</td>
          <td>Cell</td>
          <td><img src="http://cn.vuejs.org/images/logo.png"  class="ui mini rounded image"/></td>
        </tr>
        <tr>
          <td>Cell</td>
          <td>Cell</td>
          <td>Cell</td>
        </tr>
      </tbody>
      <!--
      <tfoot> 分页 </tfoot>
      -->
    </table>
</template>

<script>
  import 'bz-semantic-ui-form'
  import 'bz-semantic-ui-table'
  import 'bz-semantic-ui-button'
  export default {
    props: {
      call_back: {
      }
    },
    components: {
    },
    data: function () {
      return {
      }
    },
    ready () {
    },
    methods: {
    }
  }
</script>
