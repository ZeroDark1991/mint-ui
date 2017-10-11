<template>
  <div class="mint-spinner-snake" :style="{
    'height': spinnerSize,
    'width': spinnerSize
    }">
    <img :style="{
	    'height': '100%',
	    'width': '100%'
	  	}"
    	src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADEAAAAwCAYAAAC4wJK5AAAEb0lEQVR4AeXZ85MjTRyA8bska9ves23btm3btm3btn3/1b3PD99UdXX1zKw6r1L1Oc50+klPJ5naajYef/78iUOuiK/2b3pIQARykY8CFCLy3xYRZ4hI+qdMLoDemIhCl+PiJSJPiUj2GDsS6UhCdZsRe/ADP/EVjSsbIcfHoB4aohGKbQUU4Bu+S8Qv3EWgMhH8e3XURAMlojEibUTkKhE/lJAxDhE5ZYxIRX0toAkibK3GUUPIByRVJEL2WJ3gKigBNW3uiVJ8MVxWq/V3JyUi3yUi27AKTRFt+x1qOb5KiHpZ1VSOiZWIXCVCX61I1DOsQn4o3mYT8VK7rH7hpPZuk61FRGrjFGqr0ERCwqpiknnI9jhmpOGy+o08dTWUkHjt/HDDKjRFhstzRiG6LB9km/EKr7EPJS7HXtMuq18oLMfXEn0V6sNn+gyR2PboIPE+p4G74aUIhrzCIiQajm+A9xLyHXvLueKFwQARp/1/GErQTgnoKDLcLpEXQo95hKEIaOfkYxx6IlDOiOpIRiailH/3IRutg5NXAjqhMwrc9sJjPHeJuYD6Ft804tHU8Op3Ep1FjNsgdXEazyRGgiQE8m/5FgKi0EYCTJPvgtZILOs31UG44xIz2tLXGvXVVyffCfnwlXfQBMzDEzwTwZhuFiIyDJPvijoIr+zgRdiBp2IDAhYifGigTL4Z4qr6SbKQE4JvBDGIrujJtTEUowxGYxjqhPAuMgnFqOGgBMnqCX1xz+C+Qb8QBBSij+hr0E9RFDzpLO6W0bkQRHRXJtnfQ4/gSadxu4xOhSCiFwaWUa/gSX1wy8NN0SsEESUYLAZ5KNY39iAMxzCDQagZwo2dilqo46AmUqr97x7yiZodgueJR2xVD5qP1biEi1hk8RO7M8ZiDLoiqSpekUm4KC6I82htaTNPwHiMU2JaIrK8gwXQCyeUyZ8X53AWvS1ENMIkTDTEDEdt+MoyUE3sxAWHyZ/BcWRaiEiUiMny+wRDzACkeX3BO2OavBKwBaUWN3UmhmGyvipKzGgkOA3Q12Xyh9ENfsOT9kBz+Ms5YT9qoSmStA1eXyY8ySGmvtOgbQyTPyUnxTlsxAM4JL9PKWfEQMzHPMxCluF2tZ2+KqLYbUPPxxmxFLkur+JaCTiI/diLNO1FWY4laKGdn4zFWIj5mIsxptWUY3tjkugKX1muy3SPYzprAfuwBynKV+kt2IQNWIdc9V5BiViAeZiDRh5v+QlVtflisUsCDkjAXsxUjulkiGirjTMCi7TVmIaoUHz9GKUEBFdhN7KVY7oaIjpo46TrqyEhnWwH5EiAehntxVDtuK7YrEeYbn7U1VBCUm1GzNdWYS+2INYhYqNHRDTmBldDuawG2fx+r19Gex0m18UrQjm2qcNqJNiISDcErIDfIWKTRKz3iPBjkrYa85BkazWmKhE79Z9HeEV47LX5ymr0s7kn/GiGrh4/1elgiGjrMXYymqM2/P+Eu8B8Q0Tev/F2thWWYDFa2n6+vwC+4DxEldAftwAAAABJRU5ErkJggg==">
  </div>
</template>

<script>
  import common from './common.vue';

  export default {
    name: 'snake',

    mixins: [common]
  };
</script>

<style lang="css">
  .mint-spinner-snake {
    animation: mint-spinner-rotate 1.1s infinite linear;
    border: 4px solid transparent;
    border-radius: 50%;
  }

  @keyframes mint-spinner-rotate {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
</style>
