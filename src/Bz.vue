<style>
  img {
    width: 60px;
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
      <tr>
        <th v-for='h in header'>{{h.name_show}}</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="b in body">
        <td v-for="h in header" v-html="showTd(h.type, b[h.name_key])">
        </td>
      </tr>
    </tbody>
    <!--
    <tfoot> 分页 </tfoot>
    -->
  </table>
</template>

<script>
  import _ from 'underscore'
  import {dateFormat} from './lib_bz/functions/time.js'
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
        header: [
          {
            name_key: 'name',
            name_show: '姓名',
            type: 'input'
          },
          {
            name_key: 'sex',
            name_show: '性别',
            type: 'radio',
            values: ['男', '女']
          },
          {
            name_key: 'avatar',
            name_show: '头像',
            type: 'img'
          },
          {
            name_key: 'birthday',
            name_show: '生日',
            type: 'datetime'
          }
        ],
        body: [
          { name: '古尸', sex: '女', avatar: 'https://follow.center/api_sp/YUhSMGNITTZMeTl3WW5NdWRIZHBiV2N1WTI5dEwzQnliMlpwYkdWZmFXMWhaMlZ6THpjMk16QTNOemM0TnpRNE9Ua3pOVE0yTUM5R1pqSnFjWEkzZWk1cWNHYz0=', birthday: 1475137305871
          },
          { name: 'liu勇', sex: '男', avatar: 'https://follow.center/api_sp/YUhSMGNITTZMeTl3WW5NdWRIZHBiV2N1WTI5dEwyMWxaR2xoTDBOMFpWUkVkRlZZUlVGQk5YQnJOUzVxY0djNmIzSnBadz09', birthday: 1475137305871
          }
        ]
      }
    },
    ready () {
    },
    methods: {
      showTd: function (type, value) {
        if (_.contains(['input', 'radio'], type)) return value
        if (type === 'img') return `<img src='${value}'></img>`
        if (type === 'datetime') return dateFormat(value, 'YYYY年MM月')
      }
    }
  }
</script>
