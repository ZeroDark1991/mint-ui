<template>
  <transition name="mint-toast-pop">
    <div class="mint-toast" v-show="visible" :class="customClass">
      <i class="mint-toast-icon iconfont" :style="{ color: iconColor }" :class="iconClass" v-if="iconClass !== ''"></i>
      <span class="mint-toast-title" :style="{ 'padding-top':  iconClass ? '0.4rem' : '0' }">{{ title }}</span>
      <span class="mint-toast-text" :style="{ 'padding-top':  title ? '0.133333rem' : '0' }">{{ message }}</span>
    </div>
  </transition>
</template>

<style>
  @component-namespace mint {
    @component toast {
      position: fixed;
      padding: 0.8rem 0.2rem;
      width: 4.266667rem;
      border-radius: 0.133333rem;
      background: rgba(0, 0, 0, 0.7);
      color: #fff;
      box-sizing: border-box;
      text-align: center;
      z-index: 1000;
      transition: opacity .3s linear;
  
      @descendent icon {
        display: block;
        text-align: center;
        font-size: 0.64rem;
      }
      
      @descendent text {
        font-size: 0.32rem;
        color: #dddddd;
        display: block;
        text-align: center;
      }

      @descendent title {
        font-size: 0.48rem;
        display: block;
        text-align: center;
      }

      @when placetop {
        top: 50px;
        left: 50%;
        transform: translate(-50%, 0);
      }
      
      @when placemiddle {
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
      }
      
      @when placebottom {
        bottom: 50px;
        left: 50%;
        transform: translate(-50%, 0);
      }
      
      @descendent pop-enter, pop-leave-active {
        opacity: 0;
      }
    }
  }
</style>

<script type="text/babel">
  export default {
    props: {
      message: String,
      title: String,
      className: {
        type: String,
        default: ''
      },
      position: {
        type: String,
        default: 'middle'
      },
      iconClass: {
        type: String,
        default: ''
      },
      iconColor: {
        type: String
      }
    },

    data() {
      return {
        visible: false
      };
    },

    computed: {
      customClass() {
        var classes = [];
        switch (this.position) {
          case 'top':
            classes.push('is-placetop');
            break;
          case 'bottom':
            classes.push('is-placebottom');
            break;
          default:
            classes.push('is-placemiddle');
        }
        classes.push(this.className);

        return classes.join(' ');
      }
    }
  };
</script>