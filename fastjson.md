---
title: fastjson
date: 2017/2/27 10:20:35 
tags:
---
## 官网 ##
https://github.com/alibaba/fastjson
## wiki ##
https://github.com/alibaba/fastjson/wiki
## Fastjson的SerializerFeature序列化属性 ##
JSON序列化，默认序列化出的JSON字符串中键值对是使用双引号，如果需要单引号的JSON字符串，[eg:String jsonString = JSON.toJSONString(map, SerializerFeature.UseSingleQuotes);] fastjson序列化时可以选择的SerializerFeature有十几个属性，可以按照自己的需要去选择使用。
## 主要的API ##
	
	package com.alibaba.fastjson;
	public abstract class JSON {
	      public static final String toJSONString(Object object);
	      public static final <T> T parseObject(String text, Class<T> clazz, Feature... features);
	}
## JSONField ##
若属性是私有的，必须有set*方法。否则无法反序列化。
https://github.com/alibaba/fastjson/wiki/JSONField

	@JSONField(name="ID")
	private int id;
	//使用format配置日期格式化
	@JSONField(format="yyyyMMdd")
	public Date date;
	//serialize/deserialize指定字段不序列化
	@JSONField(serialize=false)
    public Date date;
	//使用ordinal指定字段的顺序
	public static class VO {
    @JSONField(ordinal = 3)
    private int f0;
    @JSONField(ordinal = 2)
    private int f1;
    @JSONField(ordinal = 1)
    private int f2;
	}

## 输入输出空值 ##
https://github.com/alibaba/fastjson/wiki/WriteNull_cn

	Model obj = ...;
	JSON.toJSONString(obj, SerializerFeature.WriteMapNullValue);
	SerializerFeature		描述
	WriteNullListAsEmpty	将Collection类型字段的字段空值输出为[]
	WriteNullStringAsEmpty	将字符串类型字段的空值输出为空字符串 ""
	WriteNullNumberAsZero	将数值类型字段的空值输出为0
	WriteNullBooleanAsFalse	将Boolean类型字段的空值输出为false