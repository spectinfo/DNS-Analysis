<template>
	<main>
		<div class="main-nav">
	          <el-menu default-active="1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose">
	          	<router-link to='/sta-info'><el-menu-item index="1"><i class="el-icon-menu"></i>当前维度展示信息</el-menu-item></router-link>
		      	<router-link to='/sta-info/space'><el-menu-item index="2"><i class="el-icon-setting"></i>空间维度展示信息</el-menu-item></router-link>
		      	<el-submenu index="3">
			        <template slot="title"><i class="el-icon-message"></i>时间维度展示信息</template>
			        <router-link to='/sta-info/time-year'><el-menu-item index="3-1">按创建域名/到期域名数量展示</el-menu-item></router-link>
			        <router-link to='/sta-info/time-update'><el-menu-item index="3-2">按更新时间频率展示</el-menu-item></router-link>
		        </el-submenu>
		        <el-submenu index="4">
			        <template slot="title"><i class="el-icon-search"></i>解析DNS和IP的相关信息</template>
			        <router-link to='/sta-info/ip-num'><el-menu-item index="4-1">域名IP的Online/Offline数量</el-menu-item></router-link>
			        <router-link to='/sta-info/ip-sur'><el-menu-item index="4-2">IP存活时长图</el-menu-item></router-link>
			        <router-link to='/sta-info/ip-fre'><el-menu-item index="4-3">恶意域名IP更换频率图</el-menu-item></router-link>
		        </el-submenu>
		    </el-menu>
    	</div>

    	<div class="main-right">
<!--     	<transition name="fade"> -->
			<div class="con-underline">
			<div class="dns-num">
				<span>当前恶意域名数量：</span> <span class="num-class">{{ dnsnum }}</span>
			</div>
			</div>
    		<router-view></router-view>
<!--     	</transition> -->
    	</div>

	</main>
</template>

<script>
	export default{
		data () {
			return{
				dnsnum:3000
			}
		}
	}
</script>

<style>
main{
	border: solid 20px #E9ECF1;
	margin-top: 50px;
	background-color: #FCFCFC;
	min-height: 855px;
	min-width: 1400px;
	display: -webkit-box;
	display: -ms-flexbox;
	display: flex;
	overflow: hidden;
}
.main-nav{
	-webkit-box-flex:1;
	-ms-flex:1;
	flex:1;
	background-color: #EEF1F6;

}
.main-right{
	-webkit-box-flex:5.5;
	-ms-flex:5.5;
	flex:5.5;
	padding: 20px 40px;
}
.con-underline{
	border-bottom: 1px solid #CCCCCC;
	height: 40px;
}
.dns-num{
	border-left: 8px solid #72b16a;
}
.dns-num span{
	padding-left: 15px;
	color: #72b16a;
}
.num-class{
	padding-left:5px!important;
	color: orange!important;
}
/* 路由切换动效 */
/*.fade-enter-active, .fade-leave-active {
  transition: all .3s;
}
.fade-enter, .fade-leave-active {
  opacity: 0;
}*/
</style>