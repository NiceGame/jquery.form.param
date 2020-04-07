# jquery.form.param
主要是为了解决json转query string的问题，本来jquery已经有方法的，但是提交到spring boot出现问题。查了一下，是格式问题，

例如，如果你有一个像这样的json对象：

{
   "beans":[
      {
         "agreemendId":1,
         "answerId":2
      }
   ]
}


JQuery 会将你的参数映射成这样：


beans[0][agreementId]=1
beans[0][answerId]=2


问题是Spring MVC需要这种的参数格式：


beans[0].agreementId=1
beans[0].answerId=2



参考
https://stackoverflow.com/questions/5900840/post-nested-object-to-spring-mvc-controller-using-json
