---
layout: post
title:  "bootstrap的学习总结"
date:  2017-01-05
categories: bootstrap
featured_image: /images/touxiang.jpg
---

## bootstrap的基础学习总结

### 菜单下拉框形式
	<li>
        <a href="#">特点</a>
            <ul>
				<li><a href="#" >Chrome</a></li>
                <li><a href="#">Firefox</a></li>
                <li><a href="#">Safari</a></li>
                <li><a href="#">Opera</a></li>
                <li><a href="#">IE</a></li>
            </ul>
	</li>
>&emsp;在做导航条的时候，.navbar-inverse类可以改变导航条的外观，变成黑底显示
>.navbar-fixed-top类可以让导航条固定在顶部，固定的导航条会遮住页面上的其他内容，除非给<body>元素设置了padding，导航条的默认高度是50px，比如设置：body{padding-top:70px;}
>

### 轮播图的制作
>carousel 轮播内容的组件
	<div id="carousel-example-generic" class="carousel slide" data-ride="carousel">
		<!-- Indicators -->
		<ol class="carousel-indicators">
			<li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
			<li data-target="#carousel-example-generic" data-slide-to="1"></li>
			<li data-target="#carousel-example-generic" data-slide-to="2"></li>
		</ol>/*对应的是轮播图下方的小点点*/
		<!-- Wrapper for slides -->
		<div class="carousel-inner" role="listbox">
			<div class="item active">
			  <img src="..." alt="...">
			  <div class="carousel-caption">
				...
			</div>
		</div>
		<div class="item">
		  <img src="..." alt="...">
		  <div class="carousel-caption">
			...
		  </div>
		</div>
		...
		</div>/*轮播组件的内容*/
		<!-- Controls -->
		<a class="left carousel-control" href="#carousel-example-generic" role="button" data-slide="prev">
			<span class="glyphicon glyphicon-chevron-left"></span>
			<span class="sr-only">Previous</span>
		</a>
		<a class="right carousel-control" href="#carousel-example-generic" role="button" data-slide="next">
			<span class="glyphicon glyphicon-chevron-right"></span>
			<span class="sr-only">Next</span>
		</a>轮播组件的左右控制标志
	</div>
>data-slide-to="0"代表索引，就是说索引是从0开始的，下面的图片中就是从0开始，如果有更多的，就1，2，3，4，5
>

### 栅格系统
>此处在divclass 中，也可以是其他的数值，只要是加起来等于12，那么就在同一行
	<div class="container">
		<div class="row">
			<div class="col-md-4">.col-md-4</div>
			<div class="col-md-4">.col-md-4</div>
			<div class="col-md-4">.col-md-4</div>
		</div>
	</div>
><hr>是添加分割线

### 标签页
	<!-- Nav tabs -->
	<ul class="nav nav-tabs" role="tablist">
	  <li role="presentation" class="active"><a href="#home" role="tab" data-toggle="tab">Home</a></li>
	  <li role="presentation"><a href="#profile" role="tab" data-toggle="tab">Profile</a></li>
	  <li role="presentation"><a href="#messages" role="tab" data-toggle="tab">Messages</a></li>
	  <li role="presentation"><a href="#settings" role="tab" data-toggle="tab">Settings</a></li>
	</ul>
	<!-- Tab panes -->
	<div class="tab-content">
	  <div role="tabpanel" class="tab-pane active" id="home">...</div>
	  <div role="tabpanel" class="tab-pane" id="profile">...</div>
	  <div role="tabpanel" class="tab-pane" id="messages">...</div>
	  <div role="tabpanel" class="tab-pane" id="settings">...</div>
	</div>

### 弹出框
	<div class="modal fade">
	  <div class="modal-dialog">
		<div class="modal-content">
		  <div class="modal-header">弹出的标题
			<button type="button" class="close" data-dismiss="modal"><span aria-hidden="true">&times;</span><span class="sr-only">Close</span></button>
			<h4 class="modal-title">Modal title</h4>
		  </div>
		  <div class="modal-body">弹出框中的内容
			<p>One fine body&hellip;</p>
		  </div>
		  <div class="modal-footer">弹出框的按钮
			<button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
			<button type="button" class="btn btn-primary">Save changes</button>
		  </div>
		</div><!-- /.modal-content -->
	  </div><!-- /.modal-dialog -->
	</div><!-- /.modal -->
>不管弹出框是在哪里显示，在哪里弹出，都是直接放在body里面
>下面是案例
	<!-- Button trigger modal -->
	<button type="button" class="btn btn-primary btn-lg" data-toggle="modal" data-target="#myModal">
	  Launch demo modal
	</button>设置按下哪个按钮的时候，弹出框出现
	<!-- Modal -->
	<div class="modal fade" id="myModal" tabindex="-1" role="dialog" aria-labelledby="myModalLabel" aria-hidden="true">
	  <div class="modal-dialog">
		<div class="modal-content">
		  <div class="modal-header">
			<button type="button" class="close" data-dismiss="modal"><span aria-hidden="true">&times;</span><span class="sr-only">Close</span></button>
			<h4 class="modal-title" id="myModalLabel">Modal title</h4>
		  </div>
		  <div class="modal-body">
			...
		  </div>
		  <div class="modal-footer">
			<button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
			<button type="button" class="btn btn-primary">Save changes</button>
		  </div>
		</div>
	  </div>
	</div>
>

### 菜单定位
	<script>
		$(document).ready(function(){
		$("#demo-navbar .dropdown-menu a").click(function(){
		var href = $(this).attr("href");
		$("#tab-list a[href='"+href+"']").tab("show");
		});
	});
	</script>

### 表单下拉
	<form role="form">
		<div class="form-group">
		  <select class="form-control">
			<option>1</option>
			<option>2</option>
			<option>3</option>
			<option>4</option>
			<option>5</option>
		  </select>
		</div>
		<div class="form-group">
		  <select multiple class="form-control">
			<option>1</option>
			<option>2</option>
			<option>3</option>
			<option>4</option>
			<option>5</option>
		  </select>
		</div>
	</form>

### 表单控件（复选框和单选按钮水平排列）
	<form role="form">
		<div class="form-group">
			<label class="radio-inline">
				<input type="radio" value="option1" name="sex">男性
			</label>
			<label class="radio-inline">
				<input type="radio" value="option2" name="sex">女性
			</label>
			<label class="radio-inline">
				<input type="radio" value="option3" name="sex">中性
			</label>
		</div>
	</form>
	
### 表单控件状态(禁用状态)
>就是在相应的控件上，为其添加属性“disabled”

### 按钮
>基本按钮（加上类名.btn）
>默认按钮（加上类名.btn-default）
	<button class="btn" type="button">基础按钮.btn</button>
	<button class="btn btn-default" type="button">默认按钮.btn-default</button>
	<button class="btn btn-primary" type="button">主要按钮.btn-primary</button>
	<button class="btn btn-success" type="button">成功按钮.btn-success</button>
	<button class="btn btn-info" type="button">信息按钮.btn-info</button>
	<button class="btn btn-warning" type="button">警告按钮.btn-warning</button>
	<button class="btn btn-danger" type="button">危险按钮.btn-danger</button>
	<button class="btn btn-link" type="button">链接按钮.btn-link</button>
	<button class="btn btn-primary btn-lg" type="button">大型按钮.btn-lg</button>
	<button class="btn btn-primary" type="button">正常按钮</button>
	<button class="btn btn-primary btn-sm" type="button">小型按钮.btn-sm</button>
	<button class="btn btn-primary btn-xs" type="button">超小型按钮.btn-xs</button>
>![button](images/btn.jpg)
	
### 图像的显示
>1、img-responsive：响应式图片，主要针对于响应式设计
>2、img-rounded：圆角图片
>3、img-circle：圆形图片
>4、img-thumbnail：缩略图片
>
















