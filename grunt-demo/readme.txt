git�����ϴ��ļ�����Ŀ¼�����
	echo 'dest' > .gitignore

grunt��ʵ����
1. ��Ҫ׼��һ��Gruntfile.js
   ����һ����򵥵�����
   module.exports=function(grunt){
	grunt.registerTask('default',function(){
		console.log('default test');	
	});
   };
2. grunt������
   module.exports=function(grunt){
	grunt.registerTask('default',function(name,age){
		//console.log('default test');	
		grunt.log.write('Hello '+name+' Everybody'+age);
	});
   };

   grunt default:1:2  
		grunt ������:����1������2
3. ���������
module.exports=function(grunt){
	grunt.registerTask('eat',function(name,age){
		for(var i=0; i<10; i++){
			console.log('eat '+i+' apple');
		}
	});
	grunt.registerTask('drink',function(){
		for(var i=0; i<3; i++){
			console.log('Drink'+i+' water')
		}	
	});
	grunt.registerTask('fuck',function(){
		console.log('A Fall ill');	
	});
	
	grunt.registerTask('default',['eat','drink','fuck']);
};
4. ��ȡconfig��ֵ
module.exports=function(grunt){
	//��ʼ��������Ϣ�����Զ������Ժ�ֵ
	grunt.initConfig({
		eat:{
			apple:4
		}	
	});
	
	grunt.registerTask('a',function(){
		var count=grunt.config.get('eat.apple');
		
		console.log(count);	
	});
};

//grunt a
5. ע��������
module.exports=function(grunt){
	//��ʼ��������Ϣ�����Զ������Ժ�ֵ
	grunt.initConfig({
		eat:{ //eat ��һ��task��
			apple:4, //������һ��target������ Ŀ��
			pear:10,
			banana:90,
			orange:100
		}	
	});
	
	//�������
	grunt.registerMultiTask('eat',function(){
		for(var i=0; i<10; i++){
			console.log('I am eating'+i+' of '+this.target+','+this.data);
		}	
	});
};

//grunt eat
6. ����ɾ��Ŀ¼
module.exports=function(grunt){
	//����һ��Ŀ¼
	grunt.registerTask('create',function(){
		grunt.file.mkdir('test');	
	});
	
	//ɾ��һ��Ŀ¼
	grunt.registerTask('delete',function(){
		grunt.file.delete('test');	
	});
};
//grunt create
//grunt delete
7. һ���򵥵�demo��ʾcopy��clean����
'use strict';
/*
	grunt С����
*/
module.exports=function(grunt){
	require('load-grunt-tasks')(grunt);
	
	var config={
		app:'app',
		dest:'dest'	
	};
	
	grunt.initConfig({
		config:config,
		copy:{
			html:{
				src:'app/index.html',
				dest:'dest/index.html'	
			},
			css:{
				src:'app/style.css',
				dest:'dest/style.css'
			},
			js:{
				src:'app/index.js',
				dest:'dest/index.js'	
			}	
		},
		
		clean:{
			dest:{
				src:['app/index.html','app/style.css','app/index.js']	
			}	
		}
	});
	
	grunt.registerTask('default',['copy','clean']);
};
// ���  load-grunt-tasks
// grunt-contrib-copy
// grunt-contrib-clean

