<template>
  <div class="page-toast">
    <h1 class="page-title">Toast</h1>
    <div class="page-toast-wrapper">
      <mt-button @click.native="openToast" size="large">点击弹出 Toast</mt-button>
      <mt-button @click.native="openToastWithIcon" size="large">点击弹出带有 icon 的 Toast</mt-button>
      <mt-button @click.native="openBottomToast" size="large">自定义 Toast 位置</mt-button>
    </div>
  </div>
</template>

<style>
  @component-namespace page {
    @component toast {
      @descendent wrapper {
        padding: 0 20px;
        position: absolute 50% * * *;
        width: 100%;
        transform: translateY(-50%);
        button:not(:last-child) {
          margin-bottom: 20px;
        }
      }
    }
  }
</style>

<script type="text/babel">
  import { Toast } from 'src/index';

  export default {
    methods: {
      openToast() {
        Toast({
          title: '哈哈',
          message: '沙发上打发斯蒂芬',
          iconClass: 'icon-error',
          iconColor: 'green',
          duration: 100000
        });
      },

      openToastWithIcon() {
        Toast({
          message: '操作成功',
          iconClass: 'icon-success'
        });
      },

      openBottomToast() {
        Toast({
          message: '提示信息',
          position: 'bottom'
        });
      }
    }
  };
</script>
