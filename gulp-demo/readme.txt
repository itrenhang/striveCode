gulp�÷���
1. gulp�İ�װ
	npm install -g gulp ȫ�ְ�װ
	npm install gulp    ȫ�ְ�װ��ϣ�ÿ����Ŀ������װ
	����밲װ��ʱ���gulpд����package.json�ļ����棬���Լ��� --save-dev
	npm install --save-dev gulp
	
2. ʹ��gulp
a). ����һ��gulpfile.js,��gulpfile�ж�������
	eg:
	var gulp=require('gulp');

	gulp.task('default',function(){
		console.log('gulp default task');	
	});
b). �ܵ���ǰgulpĿ¼�£�����gulp�������gulp default
3. gulp���õ�api
	gulp.task()
	gulp.src();
	gulp.desc();
	gulp.watch();

gulp.src(['js/*.js','css/*.css','*.html']) ��ȡ����Ҫ�������ļ�
	gulp.src(globs[, options])
gulp.desc(); ������д�ļ���
	gulp.dest(path[,options])

gulp.task(); ��������

gulp.watch()���������ļ��ı仯�����ļ������仯�����ǿ�����������ִ����Ӧ�����������ļ�ѹ����


	