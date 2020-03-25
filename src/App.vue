<template>
  <div id="app">
    <PersonnelGroup></PersonnelGroup>
  </div>
</template>


<script>
// import HelloWorld from './components/HelloWorld'
import PersonnelGroup from './components/PersonnelGroup'

export default {
  name: 'App',
  components: {
    PersonnelGroup,
  }
}
</script>

<style>
*{margin:0;padding: 0;}
html, body, form, h1, h2, h3, h4, h5, h6, div, dl, dt, dd, ul, ol, li, p, em, address, a, input, textarea, span, strong, img{margin: 0px;padding: 0px}
body{font-size: 12px;color: #333;font-family:"微软雅黑";}
ul,li,ol{list-style: none}
input, textarea, select, button{font-size: 12px}
img{border: none}
a{color: #333;text-decoration: none;outline: none;-webkit-transition: color 0.5s ease;-moz-transition: color 0.5s ease;-o-transition: color 0.8s ease;transition: color 0.5s ease;}
table{border-collapse: collapse}
table, thead, tbody, tfoot, tr, td{margin: 0px}
.clear{clear: both;height: 0px;line-height: 0px;font-size: 0px;overflow: hidden;visibility: hidden}
/*h1, h2, h3, h4, h5, h6{font-size: 12px;font-weight: normal}*/
h2{margin: 20px 0 10px 0;}
h4{color: #666;}
i,em{font-style: normal;}
::selection{background: #6f346a;color: #fff}
::-moz-selection{background:#6f346a;
color:#fff}
::-webkit-selection{background:#6f346a;
color:#fff}
section, article, aside, header, footer, nav, dialog, figure{display: block;}
.clearfix:after{content:".";display:block;height:0;clear:both;visibility:hidden;}
.clearfix{*+height:1%;}
a{text-decoration: none;font-size:14px;color:#000;}
li{list-style: none;}
.fl{float: left;}
.fr{float: right;}
.po_rel{position: relative;}
.po_abs{position: absolute;}
.pl_40{padding-left: 40px;}
.pr_40{padding-right: 40px;}
#app {

  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
