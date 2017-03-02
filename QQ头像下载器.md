---
title: QQ头像下载器 
date: 2017-02-14 09:52:11
tags:
---

## 根据QQ号获取QQ头像 ##
    http://ptlogin2.qq.com/getface?keytpye=0&uin=123456789&imgtype=3&r=0.4319840538403905
## 使用JSOUP批量下载QQ头像 ##
	public class QQlogo {
		private static FileOutputStream out;
	
		public static void main(String[] args) {
			try {
				String qq;
	
				for (int i = 200000; i <= 200100; i++) {
					qq = i + "";
					String url = "http://ptlogin2.qq.com/getface?keytpye=0&uin="
							+ qq + "&imgtype=3&r=0.4319840538403905";
					Document doc;
					doc = Jsoup
							.connect(url)
							.ignoreContentType(true)
							.userAgent(
									"Mozilla/5.0 (Windows; U; Windows NT 5.1; zh-CN; rv:1.9.2.15)")
							.timeout(1000).get();
					String html = doc.text();
					System.out.println(html);
					String string = html.substring(html.indexOf("\":\"") + 3,
							html.length() - 4);
					string = string.replace("\\", "");
					System.out.println(string);
					downloadImg(qq, string);
				}
	
			} catch (Exception e) {
				e.printStackTrace();
			}
	
		}
	
		private static void downloadImg(String qq, String imgUrl)
				throws MalformedURLException, IOException, FileNotFoundException {
			URL url = new URL(imgUrl);
			URLConnection uc = url.openConnection();
			InputStream is = uc.getInputStream();
			File file = new File("C:\\dminter\\me\\Me\\JavaUtils\\imgs" + "/" + qq
					+ ".png");
			out = new FileOutputStream(file);
			int i = 0;
			while ((i = is.read()) != -1) {
				out.write(i);
			}
			is.close();
		}
	}
![图例](http://i.imgur.com/7bprZHF.png)
