---
title: Java工具类
date: 2017-02-14 09:52:11
tags:
---
## map遍历 ##
	public class TestMap {
		public static void main(String[] args) {
			// TODO Auto-generated method stub
			Map<String, String> map = new HashMap<String, String>();
			map.put("1", "11");
			map.put("2", "22");
			map.put("2", "13");
			map.put("4", "44");
			// one
			Set<String> key = map.keySet();
			for (Iterator<String> it = key.iterator(); it.hasNext();) {
				String s = (String) it.next();
				System.out.println("key:" + s + " value:" + map.get(s));
			}
			//two
			for (Entry<String, String> entry : map.entrySet()) {
				System.out.println("Key = " + entry.getKey() + ", Value = "
						+ entry.getValue());
			}
			//three
			// 遍历map中的键
			for (String myKey : map.keySet()) {
				System.out.println("Key = " + myKey);
			}
			// 遍历map中的值
			for (String value : map.values()) {
				System.out.println("Value = " + value);
			}
		}
	}
## list not null ##
	public static <T> boolean listNotNull(List<T> t) {
	        return t != null && t.size() > 0;
	    }