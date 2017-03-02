---
title: retrofit
date: 2/14/2017 4:12:21 PM 
tags:
---
## retrofit-简洁高效网络请求库 ##
[http://square.github.io/retrofit/](http://square.github.io/retrofit/ "retrofit")

A type-safe HTTP client for Android and Java
将 REST API 转换为 Java 接口
## 简单用法 ##

	public interface RetrofitInterface {
	
	    // 异步带回调
	    @GET("/api/user")
	    User getUser(@Query("user_id") int userId, Callback<User> callback);
	
	    // 同步
	    @POST("/api/user/register")
	    User registerUser(@Body User user);
	}
	
	
	// 例子
	RetrofitInterface retrofitInterface = new RestAdapter.Builder()
	            .setEndpoint(API.API_URL).build().create(RetrofitInterface.class);
	
	// 获取 id 为 xxx 的用户
	retrofitInterface.getUser(xxx, new Callback<User>() {
	    @Override
	    public void success(User user, Response response) {
	
	    }
	
	    @Override
	    public void failure(RetrofitError retrofitError) {
	
	    }
	});
