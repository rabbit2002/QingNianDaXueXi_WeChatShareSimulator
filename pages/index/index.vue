<template data="name">
	<!-- <cu-custom bgColor="bg-gradual-pink" :isBack="true">
		<block slot="backText">返回</block>
		<block slot="content">表单</block>
	</cu-custom> -->
	
	<view id="dxx">
		<view class="mainDiv">
			<view class="mainDivLeft">
				<view class="avatar">
					<img v-bind:src="avatarPic">
				</view>
			</view>
			<view class="mainDivRight">
				<view class="nickName" >{{nickName}}</view>
				<view class="word">
					<p>{{wordArray.College}}</p>
					<p>{{wordArray.greadAndClass}}</p>
					<p class="operatonFontColor">{{wordArray.id}}</p>
					<p>{{wordArray.name}}</p>
				</view>
				<view class="link">
					<view class="linkPic">
						<img src="http://qqadapt.qpic.cn/adapt/0/f86d7317-9560-a7ef-8326-96c1581da40d/">
					</view>
					<view class="linkText">
						<p>{{linkText}}</p>
					</view>
				</view>
				<view class="timeAndOption">
					<view class="time">{{time}}</view>
					<view class="option operatonFontColor">删除</view>
				</view>
			</view>
		</view>
	
		<view class="inputarea">
				<view class="cu-form-group">
					<view class="title">头像链接</view>
					<input v-model="avatarPic" placeholder="" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">昵称</view>
					<input v-model="nickName" placeholder="" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">转发缩略图链接</view>
					<input v-model="linkPic" placeholder="" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">转发链接文字</view>
					<input v-model="linkText" placeholder="" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">时间</view>
					<input v-model="time" placeholder="时间" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">学校</view>
					<input v-model="wordArray.College" placeholder="" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">学院</view>
					<input v-model="wordArray.greadAndClass" placeholder="" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">学号</view>
					<input v-model="wordArray.id" placeholder="" name="input"></input>
				</view>
				<view class="cu-form-group">
					<view class="title">姓名</view>
					<input v-model="wordArray.name" placeholder="" name="input"></input>
				</view>
				
			</view>
	</view>
	
	
	
	
</template>

<script>
	export default {
		name: 'dxx',
		data() {
			return {
				msg : '12',
				avatarPic: "https://www.rabbit2002.moe/Ayano.jpg",
				nickName: 'rabbit2002',
				linkPic: "http://qqadapt.qpic.cn/adapt/0/f86d7317-9560-a7ef-8326-96c1581da40d/",
				linkText: '我完成了"青年大学习"网上主题团课第九季第二期，你也来试试吧',
				time: this.getTime(),
				wordArray: {
				    College: "XXX学校",
				    greadAndClass: "XXX学院",
				    id: 12345678910,
				    name: "XXX",
				},
			}
		},
		onLoad() {
	
		},
		methods: {
			getTime() {
			                    var date = new Date();
								if(date.getMinutes()>9){
									var time = date.getHours() + ":" + date.getMinutes();
								}else{
									
									var time = date.getHours() + ":"+ "0" + date.getMinutes();
								}
			                    return time;
			                },
		}
	}
</script>

<style>
	.cu-form-group .title {
		min-width: calc(4em + 15px);
	}
	.mainDiv {
		width: 100%;
		height: 220px;
		background-color: #FFFFFF;
	}
	.mainDivLeft {
		float: left;
		width: 20%;
		height: 100%;
		/* background-color: #007AFF; */
	}
	.mainDivRight {
		float: left;
		width: 80%;
		height: 100%;
		/* background-color: #aa55ff; */
	}
	.inputarea {
		width: 100%;
		/* height: 400px; */
	}
	.avatar {
	    width: 70px;
	    height: 70px;
	}
	
	.avatar>img {
	    width: 60px;
	    height: 60px;
	    margin-left: 8px;
	    margin-right: 8px;
		margin-top: 8px;
	    border-radius: 10px;
	}
	
	.nickName {
	    width: 100px;
	    height: 30px;
	    line-height: 30px;
	    color: rgb(88, 107, 149);
		/* background-color: #1CBBB4; */
	}
	
	.word {
	    /* width=865px */
	    width: 100%;
	    height: 80px;
	    padding-top: 2px;
		/* background-color: #39B54A; */
	}
	
	.word>p {
	    width: 100%;
	    /* fontSize=38 MarginTop/MarginBottomToFont=12 */
	    height: 20px;
	    line-height: 10px;
	    /* word-break: normal; */
	}
	
	.link {
	    /* width=865 height=167 */
	    width: 100%;
	    height: 68px;
	    margin-top: 2px;
	    padding: 4px;
	    background-color: rgb(247, 247, 247);
	}
	
	.linkPic {
	    float: left;
	    width: 60px;
	    height: 60px;
	}
	
	.linkPic>img {
	    width: 60px;
	    height: 60px;
	}
	
	.linkText {
	    float: left;
	    width: 220px;
	    height: 60px;
	    margin-left: 10px;
	}
	
	.linkText>p {
	    width: 100%;
	    height: 60px;
	    /* fontSize不确定，应该是36 */
	    font-size: 12px;
	    line-height: 18px;
	    /* 1行文字 */
	    /* margin-top: 50px; */
	    /* margin-bottom: 50px; */
	    /* 2行文字 */
		letter-spacing:1px;
	    margin-top: 12px;
	    margin-bottom: 2px;
	}
	
	.timeAndOption {
	    width: 100%;
	    height: 34px;
	    /* margin-bottom: 2px; */
		/* background-color: #1CBBB4; */
	}
	
	.time {

	    width: 40px;
	    height: 100%;
	    font-size: 14px;
	    line-height: 60px;
		float: left;
	    /* text-align: center; */
	    color: rgb(130, 130, 130);
	}
	
	.option {
	    /* float: left; */
	    width: 40px;
	    height: 100%;
		float: left;
	    margin-left: 4px;
	    font-size: 14px;
	    line-height: 60px;
	}
	
	.operatonFontColor {
	    color: rgb(90, 107, 141);
	}
	
</style>
