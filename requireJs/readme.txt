һ��requirejs��jquery�ļ����

	require.config({
		baseUrl:'./', //��Ե�Ŀ¼
		paths:{
			jquery:[ //���ȷ��ʵ�һ������һ�����ܷ��ʣ����ʵڶ���
				'http://apps.bdimg.com/libs/jquery/2.1.4/jquery.min.js',
				'lib/jquery-1.7.2'
			]	
		}	
	});

	require(['jquery'],function($){ //require() requirejs() ������
		$('body').css('background','red');
	});

����r.js�ļ�ʹ�ã�
1. ����r.js
   http://requirejs.org/docs/download.html#rjs
	�ŵ�Ҫ�����Ŀ¼
2. ʹ��(���Ƽ�)
   node r.js -o baseUrl=./ name=main out=main-build.js
3. ����ֱ�����������ṩ�������ã�Ҳ���Խ�����д��һ���ļ����ٶ��ļ���Ϊbuild.js.
  ({
    baseUrl: "js",  /*��ǰ��Ե�·��*/
    name: "main", /* �����������ļ�*/
    out: "dest/main-build.js"  /*�������ļ����Լ�Ŀ¼*/
   })
   Ȼ��ֱ�����У�node r.js -o build.js

