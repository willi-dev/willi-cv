<template>
  <div class="loading-container ">
    <div class="spinner"></div>
  </div>
</template>

<script>
export default {
  name: 'loading',
};
</script>

<style lang="scss">
.loading-container{
  position: relative;
  text-align: center;
  padding: 50px 0;
  -webkit-animation: rotation 2s infinite linear;
}
@-webkit-keyframes rotation {
    to {
        -webkit-transform: rotate(360deg);
    }
}
@keyframes spinner {
  to {transform: rotate(360deg);}
}
.spinner:before {
  content: '';
  box-sizing: border-box;
  position: absolute;
  top: 50%;
  left: 50%;
  border-radius: 50%; 
  width:20px;
  height: 20px;
  margin-top: -10px;
  margin-left: -10px;
  border: 2px solid #ccc;
  border-top-color: #333;
  animation: spinner .6s linear infinite;
}
// .style-1{
//     width:20px;
//     height: 20px;
//     margin-top: -10px;
//     margin-left: -10px;
//     border: 2px solid #ccc;
//     border-top-color: #333;
//     animation: spinner .6s linear infinite;
//     &.spinner:before {
//       content: '';
//       box-sizing: border-box;
//       position: absolute;
//       top: 50%;
//       left: 50%;
//       border-radius: 50%; 
//     }
//   }
// .style-2{
//   width: 30px;
//   height: 30px;
//   margin-top: -15px;
//   margin-left: -15px;
//   border: 1px solid #ccc;
//   border-top-color: #07d;
//   animation: spinner .6s linear infinite;
// }
// .style-3{
//   width: 20px;
//   height: 20px;
//   margin-top: -10px;
//   margin-left: -10px;
//   border: 2px solid transparent;
//   border-top-color: #07d;
//   border-bottom-color: #07d;
//   animation: spinner .8s ease infinite;
// }

</style>
