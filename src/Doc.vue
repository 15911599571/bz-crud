<template>
  <div>
    <doc :name="name"
    :desc="desc"
    :parm_desc="parm_desc"
    :parms="parms"
    :code="code"
    >
    <bz :call_back="call_back"></bz>
    </doc>
  </div>
</template>
<script>
  import Bz from './Bz'
  import Doc from 'bz-doc'
  export default {
    components: {
      Bz,
      Doc
    },
    data: function () {
      return {
        datas: [1],
        name: 'bz-crud',
        desc: 'CRUD',
        parms: [
          {parm: '', desc: 'crud操作'}
        ],
        parm_desc: `注意，如果使用的组件有路由，那么最好在切换路由的时候发送消息，解除绑定(参看本例子) <code>this.$broadcast('unbind-scroll')</code>`,
        code: `<crud  :call_back="call_back"></crud>`
      }
    },
    methods: {
      call_back: function () {
        console.log('crud')
      }
    }
  }
</script>
