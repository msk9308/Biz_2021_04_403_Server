# web.xml
## Java EE(Enterprise Edition) 프로젝트에서 Servlet,
Controller등을 관리하는 서버 설정 파일 
* @WebServlet() Annotation이 만들어지기 전에는 
Servlet,Controller 관련정보를 web.xml파일에 설정했었다
* @webServlet() Annotation을 사용하기 때무넹 굳이 web.xml을 
사용하지 않아도 프로젝트를 실행하는데 문제가 없다 
* 다만 슬래시(/, root Path)로 접근하는 경로를 Catch 하는
Controller가 없을때에는 아무런 문제가 없다
* 지금 프로젝트 HomeController에서 슬래시(/, root Path)를 
직접 핸들림하고 있기 때문에 모든파일(이미지, Css, Html등등)의 
요청을 할 수 없게 되어버렸다
#이미지, CSS파일을 JSP에서 Link하려면 Controller가 직접
핸들링 하지 못하도록 만들어 줘야 한다
* Controller가 직접 핸들링 하지 않고 CSS등을 link하기 위해서
web.xml에 default mapping을 선언해 주어야 한다.

## Web.xml을 사용한  Controller 설정
<servlet>
	<servlet-name>home</servlet-name]
	<servlet- class>com.callor.diet.HomeController</servlet-class>
	</servlet>
	<servlet-mapping>
		<serrvlet=name>home</servlet-name>
		<url-pattern>/*</url-pattern>
	</servlet-mapping>
