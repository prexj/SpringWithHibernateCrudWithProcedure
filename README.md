# springmvc-3-hello-world
Day 4 - Spring MVC 3.0 - SpringWithHibernateCrudWithProcedure Example

> In this tutorial you will know how to create Spring 3.0 MVC SpringWithHibernateCrudWithProcedure example in simplest way.


### Project Structure

![](extra/projectStructure.JPG)


#### Step 1 - Let’s Setup Environment

1. Spring 3.2.13.RELEASE and any latest version
2. Maven 3 and any latest version
3. JDK 1.6 / JDK 1.7 / JDK 1.8 / JDK 1.9
4. Eclipse Kepler / Eclipse Juno / Eclipse Neon
5. Tomcat 6 / Tomcat 7 / Tomcat 8 / Tomcat 9

#### Step 2 - Create Project

> Click on File > New > Dynamic Web Project

####![](extra/step2.1.JPG)
####![](extra/step2.2.JPG)
####![](extra/step2.3.JPG)


#### Step 3 - Convert as Maven Project

> Click Right click on Project > Configure > Convert to Maven project

####![](extra/step3.1.JPG)
####![](extra/step3.2.JPG)


#### Step 4 - Add Dipendency in ``pom.xml`` file

```XML
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.spring</groupId>
	<artifactId>controller</artifactId>
	<name>SpringWithHibernateCrud123</name>
	<packaging>war</packaging>
	<version>1.0.0-BUILD-SNAPSHOT</version>
	<properties>
		<java-version>1.6</java-version>
		<org.springframework-version>4.1.6.RELEASE</org.springframework-version>
		 <hibernate.version>4.3.10.Final</hibernate.version>
        <mysql.connector.version>5.1.31</mysql.connector.version>
		<org.aspectj-version>1.6.10</org.aspectj-version>
		<org.slf4j-version>1.6.6</org.slf4j-version>
	</properties>
	<dependencies>
		<!-- Spring -->
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-context</artifactId>
			<version>${org.springframework-version}</version>
			<exclusions>
				<!-- Exclude Commons Logging in favor of SLF4j -->
				<exclusion>
					<groupId>commons-logging</groupId>
					<artifactId>commons-logging</artifactId>
				 </exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-webmvc</artifactId>
			<version>${org.springframework-version}</version>
		</dependency>
				
		<!-- AspectJ -->
		<dependency>
			<groupId>org.aspectj</groupId>
			<artifactId>aspectjrt</artifactId>
			<version>${org.aspectj-version}</version>
		</dependency>	
		<!-- Hibernate -->
        <dependency>
            <groupId>org.hibernate</groupId>
            <artifactId>hibernate-core</artifactId>
            <version>${hibernate.version}</version>
        </dependency>
        		<!--jeckson  -->
		 <dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-core</artifactId>
			<version>2.2.3</version>
		</dependency>
		<dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-databind</artifactId>
			<version>2.2.3</version>
		</dependency>
		<dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-annotations</artifactId>
			<version>2.2.3</version>
		</dependency>
			    
			<dependency>
			    <groupId>org.codehaus.jackson</groupId>
			    <artifactId>jackson-core-asl</artifactId>
			    <version>1.9.13</version>
			</dependency>
			
			<dependency>
			    <groupId>org.codehaus.jackson</groupId>
			    <artifactId>jackson-mapper-asl</artifactId>
			    <version>1.9.13</version>
			</dependency>
        <!--orm  -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-orm</artifactId>
            <version>${org.springframework-version}</version>
        </dependency>
		
		<!-- Logging -->
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-api</artifactId>
			<version>${org.slf4j-version}</version>
		</dependency>
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>jcl-over-slf4j</artifactId>
			<version>${org.slf4j-version}</version>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>org.slf4j</groupId>
			<artifactId>slf4j-log4j12</artifactId>
			<version>${org.slf4j-version}</version>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>log4j</groupId>
			<artifactId>log4j</artifactId>
			<version>1.2.15</version>
			<exclusions>
				<exclusion>
					<groupId>javax.mail</groupId>
					<artifactId>mail</artifactId>
				</exclusion>
				<exclusion>
					<groupId>javax.jms</groupId>
					<artifactId>jms</artifactId>
				</exclusion>
				<exclusion>
					<groupId>com.sun.jdmk</groupId>
					<artifactId>jmxtools</artifactId>
				</exclusion>
				<exclusion>
					<groupId>com.sun.jmx</groupId>
					<artifactId>jmxri</artifactId>
				</exclusion>
			</exclusions>
			<scope>runtime</scope>
		</dependency>

		<!-- @Inject -->
		<dependency>
			<groupId>javax.inject</groupId>
			<artifactId>javax.inject</artifactId>
			<version>1</version>
		</dependency>
				
		<!-- Servlet -->
		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>servlet-api</artifactId>
			<version>2.5</version>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>javax.servlet.jsp</groupId>
			<artifactId>jsp-api</artifactId>
			<version>2.1</version>
			<scope>provided</scope>
		</dependency>
		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>jstl</artifactId>
			<version>1.2</version>
		</dependency>
		 <!-- jsr303 validation -->
        <dependency>
            <groupId>javax.validation</groupId>
            <artifactId>validation-api</artifactId>
            <version>1.1.0.Final</version>
        </dependency>
        <dependency>
            <groupId>org.hibernate</groupId>
            <artifactId>hibernate-validator</artifactId>
            <version>5.1.3.Final</version>
        </dependency>
 
        <!-- MySQL -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>${mysql.connector.version}</version>
        </dependency>
	
		<!-- Test -->
		<dependency>
			<groupId>junit</groupId>
			<artifactId>junit</artifactId>
			<version>4.7</version>
			<scope>test</scope>
		</dependency>        
	</dependencies>
    <build>
        <plugins>
            <plugin>
                <artifactId>maven-eclipse-plugin</artifactId>
                <version>2.9</version>
                <configuration>
                    <additionalProjectnatures>
                        <projectnature>org.springframework.ide.eclipse.core.springnature</projectnature>
                    </additionalProjectnatures>
                    <additionalBuildcommands>
                        <buildcommand>org.springframework.ide.eclipse.core.springbuilder</buildcommand>
                    </additionalBuildcommands>
                    <downloadSources>true</downloadSources>
                    <downloadJavadocs>true</downloadJavadocs>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>2.5.1</version>
                <configuration>
                    <source>1.6</source>
                    <target>1.6</target>
                    <compilerArgument>-Xlint:all</compilerArgument>
                    <showWarnings>true</showWarnings>
                    <showDeprecation>true</showDeprecation>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.codehaus.mojo</groupId>
                <artifactId>exec-maven-plugin</artifactId>
                <version>1.2.1</version>
                <configuration>
                    <mainClass>org.test.int1.Main</mainClass>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
```

#### Step 5 - Add Spring Servlet context in ``Deployed Resources\WEB-INF\spring\appServlet\servlet-context.xml`` file

```XML
<?xml version="1.0" encoding="UTF-8"?>
<beans:beans xmlns="http://www.springframework.org/schema/mvc"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xmlns:beans="http://www.springframework.org/schema/beans"
	xmlns:context="http://www.springframework.org/schema/context"
	xsi:schemaLocation="http://www.springframework.org/schema/mvc http://www.springframework.org/schema/mvc/spring-mvc.xsd
		http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">

	<!-- DispatcherServlet Context: defines this servlet's request-processing infrastructure -->
	
	<!-- Enables the Spring MVC @Controller programming model -->
	<annotation-driven />
	<beans:bean id="propertyConfigurer" class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer">
	  <beans:property name="ignoreUnresolvablePlaceholders" value="true"/>
		<beans:property name="locations">
			<beans:list>
				<beans:value>classpath:database.properties</beans:value><!-- "src/main/webapp/WEB-INF/spring/appServlet/database.properties" -->
			</beans:list>
		</beans:property>
	</beans:bean>
	
	<!-- <tx:annotation-driven transaction-manager="hibernateTransactionManager"/> -->
	<beans:bean id="transactionManager" class="org.springframework.orm.hibernate4.HibernateTransactionManager" >
		<beans:property name="sessionFactory" ref="sessionFactory"></beans:property>
	</beans:bean>
	<!-- <tx:annotation-driven transaction-manager="transactionManager"/> -->

	<!-- <context:property-placeholder location="classpath:database.properties"/> -->
	<!-- </context:property-placeholder> -->
	<context:component-scan base-package="com.spring"/>
	
	<!-- </context:component-scan> -->
	
	<beans:bean class="org.springframework.jdbc.datasource.DriverManagerDataSource" id="dataSource">
		 <beans:property name="driverClassName" value="${driverClassName}"></beans:property>
		 <beans:property name="url" value="${url}"></beans:property>
		 <beans:property name="username" value="${username}"></beans:property>
		 <beans:property name="password" value="${password}"></beans:property>
	</beans:bean>
	<beans:bean class="org.springframework.orm.hibernate4.LocalSessionFactoryBean" id="sessionFactory">
			<beans:property name="dataSource" ref="dataSource"></beans:property>
			<beans:property name="annotatedClasses">
				  <beans:list>
				   <beans:value>com.pratikJoshi.spring.model.Employee</beans:value>
				  </beans:list>
 			</beans:property>
	<beans:property name="hibernateProperties">
		<beans:props>
			  <beans:prop key="hibernate.dialect">org.hibernate.dialect.MySQL5Dialect</beans:prop>
			  <beans:prop key="hibernate.show_sql">true</beans:prop>
			  <beans:prop key="hibernate.hbm2ddl.auto">update</beans:prop> 
			   <!-- <mapping class="com.spring.model.Employee"/>   --> 
		</beans:props>
	</beans:property>
</beans:bean>
<beans:bean class="org.springframework.orm.hibernate4.HibernateTransactionManager" id="hibernateTransactionManager">
 <beans:property name="sessionFactory" ref="sessionFactory"></beans:property>
  </beans:bean>

	<!-- Handles HTTP GET requests for /resources/** by efficiently serving up static resources in the ${webappRoot}/resources directory -->
	<resources mapping="/resources/**" location="/resources/" />

	<!-- Resolves views selected for rendering by @Controllers to .jsp resources in the /WEB-INF/views directory -->
	<beans:bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
		<beans:property name="prefix" value="/WEB-INF/views/" />
		<beans:property name="suffix" value=".jsp" />
	</beans:bean>
	
	<context:component-scan base-package="com.pratikJoshi" />
	
	
	
</beans:beans>
```

#### Step 6 - Add Spring Servlet in ``WebContent\WEB-INF\web.xml`` file

```XML
<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.5" xmlns="http://java.sun.com/xml/ns/javaee"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">

	<!-- The definition of the Root Spring Container shared by all Servlets and Filters -->
	<context-param>
		<param-name>contextConfigLocation</param-name>
		<param-value>/WEB-INF/spring/root-context.xml</param-value>
	</context-param>
	
	<!-- Creates the Spring Container shared by all Servlets and Filters -->
	<listener>
		<listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
	</listener>

	<!-- Processes application requests -->
	<servlet>
		<servlet-name>appServlet</servlet-name>
		<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
		<init-param>
			<param-name>contextConfigLocation</param-name>
			<param-value>/WEB-INF/spring/appServlet/servlet-context.xml</param-value>
		</init-param>
		<load-on-startup>1</load-on-startup>
	</servlet>
		
	<servlet-mapping>
		<servlet-name>appServlet</servlet-name>
		<url-pattern>/</url-pattern>
	</servlet-mapping>

</web-app>
```

#### Step 7 - Add View to project ``Deployed Resources\WEB-INF\view\emp.jsp`` file spring\appServlet\servlet-context.xml

```JSP
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
    <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
<title>Insert title here</title>
	<link href="http://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" rel="stylesheet"> 
	<script src="http://code.jquery.com/jquery-1.10.2.js"></script>
	<script src="http://code.jquery.com/ui/1.10.4/jquery-ui.js"></script>
	<!-- CSS -->
	<style>
	Table.GridOne 
		{
		 padding: 3px;
		 margin: 0;
		 background: lightyellow;
		 border-collapse: collapse; 
		 width:35%;
		}
	Table.GridOne Td 
		{ 
		 padding:2px;
		 border: 1px solid #ff9900;
		 border-collapse: collapse;
		} 
	</style>
	<script type="text/javascript">
	
	jQuery(document).ready(function() {
		$('#insertBut').hide();
		$('#updateBut').hide();
		
		showAll();
		
	    jQuery("#confirmationDialog").dialog({
	        autoOpen: false,
	        modal: true,
	        title:'insert Data',
	        width:600,
	        height:600,
	        open: function() {
	        	var id = $("#id").val();
	        	if(id == '' ){
	        		$('#insertBut').show();
	        		$('#updateBut').hide();
	        	}else{
	        		$('#insertBut').hide();
	        		$('#updateBut').show();
	        	}
	        },
	        close :function() {
	        	$("#id").val('');
    	    	$("#fname").val('');
    	    	$("#lname").val('');
    	    	$("#gen").val('');
    	    	$("#address").val('');
    	    	
	        	showAll();
	        } 
	    });
	});
	
	function insert(){
		$("#confirmationDialog").dialog("open");
	}
	
	function showAll(){
	      $.ajax({
	              type:"GET",
	              url:"showAll",
	              dataType: "json",
	              success:function(data)
	              { 
	            	  var rows = '';
	                  $.each( data , function( index, item ) {
	                	rows += '<tr><td>' + item.id + '</td>';
	          	  	  	rows += '<td>' + item.firstname + '</td>';
	          	  	  	rows += '<td>' + item.lastname + '</td>';
	          	  	  	rows += '<td>' + item.gender + '</td>';
	          	  		rows += '<td>' + item.address + '</td>';
	          	  		rows += '<td onclick="editAjaxData('+item.id+');" >edit</td>';
	          	  		rows += '<td onclick="showAjaxData('+item.id+');" >show single emp</td>';
	          	  		rows += '<td onclick="deleteAjaxData('+item.id+');" >Delete</td></tr>';
	          	  	  	
	          	  	  });
	          	  	  $('#tblProducts').html(rows);
	              },
	              error:function(xmlHttpRequest, textStatus, errorThrown)
	              {
	                     alert("error");
	              }
	      });
	}
	
	function insertAjaxData(){
    	var fn = $("#fname").val();
  		var ln = $("#lname").val();
  		var gn = $("#gen").val();
  		var add = $("#address").val();
    	$.ajax({
	    	   type: "post",
	    	   url: "insertInfo",
	    	   dataType: "json",  
	    	   data:{fname: fn , lname: ln , gen: gn , address: add},
	    	   success: function(response){
	    	    if(response == 1){
	    	    	
	    	    	alert('inserted');
	    	    	$('#confirmationDialog').dialog('close');
	    	    	showAll();
	    	    }
	    	   },
	    	   error: function(){      
	    	    alert('Error while request..');
	    	   }
	    });
    }
	function updateAjaxData(){
		var id = $("#id").val();
    	var fn = $("#fname").val();
  		var ln = $("#lname").val();
  		var gn = $("#gen").val();
  		var add = $("#address").val();
    	$.ajax({
	    	   type: "post",
	    	   url: "updateInfo",
	    	   dataType: "json",  
	    	   data:{id: id, fname: fn , lname: ln , gen: gn , address: add},
	    	   success: function(response){
	    	    if(response == 1){
	    	    	alert('updated');
	    	    	$('#confirmationDialog').dialog('close');
	    	    	showAll();
	    	    }
	    	   },
	    	   error: function(){      
	    	    alert('Error while request..');
	    	   }
	    });
    }
	
	function showAjaxData(id){
		$.ajax({
            type:"GET",
            url:"showSingleEmp",
            dataType: "json",
            data:{id: id },
            success:function(data)
            { 
          	  var rows = '';
                //$.each( data , function( index, item ) {
                	console.log('item.id'+data.id);
                	console.log('item.firstname'+data.firstname);
                	console.log('item.lastname'+data.lastname);
                	console.log('item.gender'+data.gender);
                	console.log('item.address'+data.address);
                	console.log('item.id'+item.dflag);
              	rows = '<tr><td>' + data.id + '</td>'
        	  	    + '<td>' + data.firstname + '</td>'+
        	  	  	'<td>' + data.lastname + '</td>'+
        	  	    '<td>' + data.gender + '</td>'+
        	  		'<td>' + data.address + '</td>'+
        	  		'<td onclick="editAjaxData('+data.id+');" >edit</td>'+
        	  		/* rows += '<td onclick="showAjaxData('+item.id+');" >show single emp</td>'; */
        	  		'<td onclick="deleteAjaxData('+data.id+');" >Delete</td></tr>';
        	  	  	
        	  	  //});
        	  	 $('#tblProducts2').html(rows);
        	  	$("#confirmationDialog2").dialog("open");
            },
            error:function(xmlHttpRequest, textStatus, errorThrown)
            {
                   alert("error");
            }
    });
	}
	function editAjaxData(id){
		alert('editAjaxData()'+id);
		
  	  $.ajax({
  	   type: "get",
  	   url: "editData",
  	   dataType: "json",  
  	   data:{id: id },
  	   success: function(response){
  		    alert(response);
  		    $("#id").val(response.id);
    		$("#fname").val(response.firstname);
    		$("#lname").val(response.lastname);
    		$("#gen").val(response.gender);
    		$("#address").val(response.address);
  	    	$("#confirmationDialog").dialog("open");
  	   },
  	   error: function(){      
  	    alert('Error while request..');
  	   }
  	  });
  	}
	
	function deleteAjaxData(id){
  	  $.ajax({
  	   type: "post",
  	   url: "deleteData",
  	   dataType: "json",  
  	   data:{id: id },
  	   success: function(response){
	  	   if(response == 1){
	  		   alert('data dleted');
	  		   showAll();
	  	   }
  	   },
  	   error: function(){      
  	   		alert('Error while request..');
  	   }
  	  });
  	 }
	</script>
</head>
<body>
	<button id="click" onclick="insert();"> Add New</button>
	<table>
	  <thead>
	  	<tr>
		  <th> Id </th>
		  <th> FirstName </th>
		  <th> Lastname </th>
		  <th> Gender </th>
		  <th> address </th>
		  <th>Action</th>
		</tr>
	  </thead>
	  <tbody id="tblProducts">
	  
	  </tbody>
	</table>
	<div id="confirmationDialog">
        <table class="GridOne">
	        <tr>
				<td>
					<input id="id" type="hidden" name="id"  value=""/>
					<label>First Name</label>
				</td> 
				<td>
					<input id="fname" type="text" name="fname"  value=""/>
				</td>         
			</tr>
			 <tr>
				<td>
					<label>Last Name</label>
				</td> 
				<td>
					<input id="lname" type="text" name="lname"  value=""/>
				</td>         
			</tr>
			 <tr>
				<td>
					<label>Gender</label>
				</td> 
				<td>
					<input id="gen" type="text" name="gen"  value=""/>
				</td>         
			</tr>
			 <tr>
				<td>
					<label>Address</label>
				</td> 
				<td>
					<textarea id="address" name="address" rows="4" cols="8" maxlength="400"></textarea>
				</td>         
			</tr>
			<tr>
				<td>
					<input type="button" id="insertBut" name="submit" onclick="insertAjaxData();" value="submit">
					<input type="button" id="updateBut" name="submit" onclick="updateAjaxData();"  value="update">
				</td>         
			</tr>
			
        </table>
</div>
<div id="confirmationDialog2">
	<table>
       <thead>
	  	<tr>
		  <th> Id </th>
		  <th> FirstName </th>
		  <th> Lastname </th>
		  <th> Gender </th>
		  <th> address </th>
		   <th> status </th>
		  <th>Action</th>
		</tr>
	  </thead>
	  <tbody id="tblProducts2">
	  
	  </tbody>
	</table>
</div>

</body>
</html>
```

![](extra/OutputOfHomePage.JPG)
#### here if click on Add new button 
1. First call emp page of insert() function we can show above jsp code here in this function open popup code.
1. After that fill up all the data.  
2. And click save button.
3. Here click save button then call insertAjaxData() function.  
4. Here this function through we can call controller And data are save in database of table.


#### Step 8 - Add Controller Class in ``src\com\pratikJoshi\spring\controller\MainController.java`` folder

> Right Click on ``src`` folder > New > Class

###![](extra/step7.1.JPG)

```JAVA
package com.pratikJoshi.spring.controller;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.text.DateFormat;
import java.util.ArrayList;
import java.util.Date;
import java.util.List;
import java.util.Locale;

import javax.transaction.HeuristicMixedException;
import javax.transaction.HeuristicRollbackException;
import javax.transaction.RollbackException;
import javax.transaction.SystemException;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.PropertySource;
import org.springframework.context.support.PropertySourcesPlaceholderConfigurer;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.ResponseBody;

import com.pratikJoshi.spring.dao.EmployeeDao;
import com.pratikJoshi.spring.model.Employee;

/**
 * Handles requests for the application home page.
 */
@Controller
/*@Configuration
@ComponentScan(basePackages="com.spring")
@PropertySource(value ={"classpath:database.properties"})*/
public class MainController {
	
	private static final Logger logger = LoggerFactory.getLogger(MainController.class);
	
	@Autowired
	EmployeeDao empDao;
	
	@RequestMapping(value = "/", method = RequestMethod.GET)
	public String home(Locale locale, Model model) {
		logger.info("Welcome home! The client locale is {}.", locale);
		return "emp";
	}
	@RequestMapping(value = "insertInfo", method = RequestMethod.POST,produces="application/json")
	@ResponseBody
	public int insertData(@RequestParam("fname")String firstname,
			@RequestParam("lname")String lastname,
			@RequestParam("address")String address,
			@RequestParam("gen") String gen, Model model) throws  RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException {
		logger.info("Welcome insertData()");
		logger.info("fname"+firstname);
		logger.info("fname"+lastname);
		logger.info("fname"+address);
		logger.info("gen"+gen);
		
		Employee empBean= new Employee();
		empBean.setFirstname(firstname);
		empBean.setLastname(lastname);
		empBean.setAddress(address);
		empBean.setDflag(1);
		empBean.setGender(gen);
		
		int i = empDao.addEmployee(empBean);
		logger.info("Welcome insertData()"+empBean);
		if(i>0){
			i = 1;
		}else{
			i = 0;
		}
		return i;
	}
	/*@RequestMapping(value = "showAll", method = RequestMethod.GET ,produces="application/json")
	@ResponseBody
	public ArrayList<Employee> showAll(Locale locale, Model model) {
		logger.info("Welcome ShowData()");
		//model.addAttribute("show", empDao.listemployee());
		ArrayList<Employee> emplist = empDao.listemployee();
		for (Employee temp : empDao.listemployee()) {
			System.out.println(temp);
		}
		return emplist;
	}*/
	@RequestMapping(value = "showAll", method = RequestMethod.GET ,produces="application/json")
	@ResponseBody
	public ArrayList<Employee> showAll(Locale locale, Model model) {
		logger.info("Welcome ShowData()");
		//model.addAttribute("show", empDao.listemployee());
		ArrayList<Employee> emplist = empDao.listemployee();
		for (Employee temp : empDao.listemployee()) {
			System.out.println(temp);
		}
		return emplist;
	}
	//showSingleEmp
	@RequestMapping(value = "showSingleEmp", method = RequestMethod.GET ,produces="application/json")
	@ResponseBody
	public Employee showSingleEmp(@RequestParam("id")int id, Model model) {
		logger.info("id is"+id);
		//model.addAttribute("editemp", empDao.getById(id));
		Employee em = empDao.getEmployeeById(id);
		System.out.println("getDflag"+em.getDflag());
		System.out.println("getAddress"+em.getAddress());
		System.out.println("getFirstname"+em.getFirstname());
		System.out.println("getLastname"+em.getLastname());
		System.out.println("getId"+em.getId());
		return em;
	}
	/*@RequestMapping(value = "findEmp", method = RequestMethod.GET)
	public String findEmp(@RequestParam("skill")String[] skill, Model model) {
		for (int i = 0; i < skill.length; i++) {
			logger.info("skill is"+skill[i]);
		}
		
		model.addAttribute("editemp", empDao.findBySkill(skill));
		return "employeelist";
	}*/
	@RequestMapping(value = "editData", method = RequestMethod.GET ,produces="application/json")
	@ResponseBody
	public Employee editEmployee(@RequestParam("id")int id, Model model) {
		logger.info("id is"+id);
		//model.addAttribute("editemp", empDao.getById(id));
		Employee em = empDao.getById(id);
		return em;
	}
	@RequestMapping(value = "deleteData", method = RequestMethod.POST ,produces="application/json")
	@ResponseBody
	public String deleteEmployee(@RequestParam("id")int id, Model model) throws SecurityException, RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException {
		logger.info("id is"+id);
		
		int i  =empDao.deleteEmp(id);
		String rtn = "";
		if(i>0){
			rtn = "1";
		}else{
			rtn ="0";
		}
		return rtn;
	}
	@RequestMapping(value = "updateInfo", method = RequestMethod.POST ,produces="application/json")
	@ResponseBody
	public int updateEmployee(@RequestParam("id")int id,
			@RequestParam("fname")String firstname,
			@RequestParam("lname")String lastname,
			@RequestParam("gen")String gen,
			@RequestParam("address")String address, Model model) throws  RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException {
		logger.info("id is"+id);
		logger.info("fname"+firstname);
		logger.info("lastname"+lastname);
		logger.info("gen"+gen);
		logger.info("address"+address);
		Employee empBean = new Employee();
		empBean.setId(id);
		empBean.setFirstname(firstname);
		empBean.setLastname(lastname);
		empBean.setAddress(address);
		empBean.setGender(gen);
		empBean.setDflag(1);
		empBean = empDao.updateEmployee(empBean);
		int i;
		 if(empBean.getId()>0){
			 return i = 1;
		 }else{
			 return i = 0;
		 }
		 
		//return i;
	}
	/*@RequestMapping(value = "serchAJAX", method = RequestMethod.GET , produces="application/json")
	@ResponseBody
	public ArrayList<Employee> serchAJAX( @RequestParam("skill") String[] skill)  {
		logger.info("serchajax()");
		for (int i = 0; i < skill.length; i++) {
			logger.info("skill is"+skill[i]);
		}
		
		
		Employee emp = null;
        //ArrayList<Employee> empFname = new ArrayList<Employee>();
        String skl =" "; 
        for (int i = 0; i < skill.length; i++) {
			skl = skl+skill[i]+"";
		}
        emp.setSkill(skl);
        ArrayList<Employee> empfname = empDao.findBySkill(emp);
        
		try {
			Class.forName("com.mysql.jdbc.Driver");
			con = DriverManager.getConnection("jdbc:mysql://localhost:3306/test", "root", "root");
			Statement st =con.createStatement();
			ResultSet rs = st.executeQuery("select * from emp where skill like '%"+skill+"%'; ");
			while( rs.next() ){
				ben = new EmployeeBen();
				ben.setFname(rs.getString("fname"));
				System.out.println(ben.getFname());
				empFname.add(ben);
			}
			 
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		return empfname;
	}*/
	 @Bean
	    public static PropertySourcesPlaceholderConfigurer propertySourcesPlaceholderConfigurer() {
	        return new PropertySourcesPlaceholderConfigurer();
	    }
	
}

```
#### Step 9 - Add dao Class in ``src\com\pratikJoshi\spring\dao\EmployeeDao.java`` folder 

> Right Click on ``src`` folder > New > Class

###![](extra/step7.1.JPG)

```JAVA
package com.pratikJoshi.spring.dao;

import java.util.ArrayList;
import java.util.List;

import javax.annotation.Resource;
import javax.persistence.ValidationMode;
import javax.transaction.HeuristicMixedException;
import javax.transaction.HeuristicRollbackException;
import javax.transaction.RollbackException;
import javax.transaction.SystemException;


import javax.transaction.Transactional;

import org.hibernate.Query;
import org.hibernate.SQLQuery;
import org.hibernate.Session;
import org.hibernate.SessionFactory;
import org.hibernate.Transaction;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

import com.pratikJoshi.spring.model.Employee;

@Component
/*@Resource
@Qualifier("empDao")
@Transactional()*/
public class EmployeeDao {
	
	@Autowired
	SessionFactory sessionFactory;

	/*public void setSessionFactory(SessionFactory sessionFactory) {
		this.sessionFactory = sessionFactory;
	}
	*/ @Transactional()
	public int addEmployee(Employee empBean) throws RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException{
		/*Session session= sessionFactory.getCurrentSession();*/
		Session session = sessionFactory.openSession();
		  Transaction tx = session.beginTransaction();
		/*Session session= sessionFactory.getCurrentSession();*/
	    int  i = (Integer) session.save(empBean);
		/*Session session = sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		String hql = "INSERT INTO Employee(firstName, lastName, address) values(?,?,?)"  + 
	             "SELECT firstName, lastName,address FROM employee400";
		
		session.save(empBean.getFirstname());
		session.save(empBean.getLastname());
		session.save(empBean.get);
	Query query = session.createQuery(hql);
	query.setParameter(1, empBean.getLastname());
	query.setParameter(2, empBean.getLastname());
	query.setParameter(3, empBean.getAddress());
	int result = query.executeUpdate();
	System.out.println("Rows affected: " + result);*/
	    tx.commit();
	    session.close();
	    System.out.println("employee saved successfully, Person Details="+empBean);
	    System.out.println("emp id is "+i);
		return i;
		}
	 @Transactional()
	public Employee updateEmployee(Employee empBean) throws RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException{
		Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
	    Employee em = (Employee) session.merge(empBean);
	    tx.commit();
	    session.close();
	    System.out.println("Employee update successfully, Person Details="+empBean);
		return em;
		}
	 /*@Transactional()
	 @SuppressWarnings("unchecked")
	public ArrayList<Employee> listemployee(){
		ArrayList<Employee> empList = new ArrayList<Employee>();
		 for(Employee empBean : empList){
	            logger.info("Person List::"+p);
	        }
		Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		String hql = "FROM Employee WHERE dflag = :dflag";
		Query query = session.createQuery(hql);
		query.setParameter("dflag",1);
		return (ArrayList<Employee>) query.list();
		//return (ArrayList<Employee>) sessionFactory.openSession().createQuery("SELECT E.* FROM Employee E WHERE E.dflag =: 1 ")
			   // .list();
		//return (ArrayList<Employee>) sessionFactory.openSession().createQuery("select id, firstname , lastname , address from Employee where dflag = 1")
			    //.list();
		}*/
	 @Transactional()
	 @SuppressWarnings("unchecked")
	public ArrayList<Employee> listemployee(){
		ArrayList<Employee> empList = new ArrayList<Employee>();
		 /*for(Employee empBean : empList){
	            logger.info("Person List::"+p);
	        }*/
		Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		//String hql = "FROM Employee WHERE dflag = :dflag";
		Query query = (Query) session.createSQLQuery("{CALL getAllEmprecord}").addEntity(Employee.class);
		//Query query1 = (Query) session.createStoredProcedu;
		//Query query = session.createQuery(hql);
		//query.setParameter("dflag",1);
		return (ArrayList<Employee>) query.list();
		/*return (ArrayList<Employee>) sessionFactory.openSession().createQuery("SELECT E.* FROM Employee E WHERE E.dflag =: 1 ")
			    .list();*/
		/*return (ArrayList<Employee>) sessionFactory.openSession().createQuery("select id, firstname , lastname , address from Employee where dflag = 1")
			    .list();*/
		}
	 @Transactional()
	public Employee getById(int id){
		return (Employee) sessionFactory.openSession().get(Employee.class, id);
		}
	 @Transactional()
	public Integer deleteEmp(int id) throws RollbackException, HeuristicMixedException, HeuristicRollbackException, SystemException{
		 System.out.println("before id :"+id +"dflag"+((Employee) sessionFactory.openSession().get(Employee.class, id)).getDflag());
	 	 /*Employee emp  = new Employee();
	 	 emp.setDflag(0);
	 	 emp.setId(id);*/
		 Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		String hql = "Update Employee set dflag = :dflag where id = "+id;
		Query query = session.createQuery(hql);
		query.setParameter("dflag",0);
		int i = query.executeUpdate();
		System.out.println("i is :::"+i);
		/*session.createQuery("update Employee E set E.dfalg = 0 where E.id ="+id).executeUpdate();*/
		//String hql = "update Employee set dfalg = 1 where id ="+ id ;
	             
		//Query query = session.createQuery(hql);
		//query.executeUpdate();
		tx.commit();
		System.out.println("after id:"+id+" dflag = "+((Employee) sessionFactory.openSession().get(Employee.class, id)).getDflag());
		if(i>0){
			i = 1;
		}else{
			i=0;
		}
		  session.close();
		return i;
	}
	/* @Transactional()
	 @SuppressWarnings("unchecked")
	public ArrayList<Employee> findBySkill(Employee emp) {
		ArrayList<Employee> empList = new ArrayList<Employee>();
		 for(Employee empBean : empList){
	            logger.info("Person List::"+p);
	        }
		Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		String hql = "FROM Employee WHERE skill = :skill";
		Query query = session.createQuery(hql);
		query.setParameter("skill",emp.getSkill());
		return (ArrayList<Employee>) query.list();
		
		
	}*/
	/* Query query = session
			 16
			                 .createSQLQuery("CALL usp_get_bug_details(:bugCode,:frmDate,:toDate)");
			 17
			         query.setParameter("bugCode", "100");
			 18
			         query.setParameter("frmDate", cal.getTime());*/

	public Employee getEmployeeById(int id) {
		Session session= sessionFactory.openSession();
		Transaction tx = session.beginTransaction();
		//String hql = "FROM Employee WHERE dflag = :dflag";
		//Query query = (Query) session.createSQLQuery("{CALL getrecord(:id)}").setParameter("id",id);
		//List result =query.list();
		//query.setParameter("id",id);
		//return (Employee) session.createSQLQuery("{CALL getrecord(:id)}").setParameter("id",id).uniqueResult();
		//Employee obj = null;
		//if(result.size()==0){
			//return new Employee();
		//}else{
			//obj = (Employee) result.get(0);
		//}
		//session.close();
		//.openSession()
		System.out.println("id"+id);
		Query query = (Query) session.createSQLQuery("{CALL getrecord(:id)}").addEntity(Employee.class);
		query.setParameter("id", id);
		List<Employee> emp =query.list();
		for (Employee employee : emp) {
			System.out.println("getFirstname"+employee.getFirstname());
			System.out.println("getGender"+employee.getGender());
			System.out.println("getDflag"+employee.getDflag());
			System.out.println("getLastname"+employee.getLastname());
			System.out.println("getIdgetId"+employee.getId());
			System.out.println("getAddress"+employee.getAddress());
		}
		Employee obj = null;
		if(emp.size()==0){
			return new Employee();
		}else{
			obj = (Employee) emp.get(0);
		}
		
		//return (Employee) session.createSQLQuery("{CALL getrecord(:id =`"+id+"`)}").addEntity(Employee.class);
		//return session.createSQLQuery("{CALL getrecord(:id =`"+id+"`}").addEntity(Employee.class);
		return  obj;
	}

}


```


#### Step 10 - Add Entity Class in ``src\com\pratikJoshi\spring\model\Employee.java`` folder 

> Right Click on ``src`` folder > New > Class

###![](extra/step7.1.JPG)

```JAVA
package com.pratikJoshi.spring.model;

import java.io.Serializable;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.Table;
import javax.persistence.TableGenerator;
import javax.persistence.Transient;

@Entity
@Table(name="employeep")
public class Employee implements Serializable{
	
	@Id
	//@TableGenerator(name="TABLE_GEN",table="T_GENERATOR",pkColumnName="GEN_KEY",pkColumnValue="TEST",valueColumnName="GEN_VALUE",initialValue=1,allocationSize=1)
	//@GeneratedValue(strategy=GenerationType.TABLE, generator="TABLE_GEN")
	@GeneratedValue(strategy=GenerationType.AUTO)
	@Column(name="id")
	private int id;
	
	@Column(name="firstname")
	private String firstname;
	
	@Column(name ="lastname")
	private String lastname;
	
	@Column(name="address")
	private String address;
	
	/*@Column(name="skill")
	private String skill;*/
	@Column(name="gender")
	private String gender;
	
	//@Transient
	@Column(name="dflag")
	private int dflag;
	
	/*public Employee()*/
	
	public int getDflag() {
		return dflag;
	}
	public void setDflag(int dflag) {
		this.dflag = dflag;
	}
	public int getId() {
		return id;
	}
	public void setId(int id) {
		this.id = id;
	}
	public String getFirstname() {
		return firstname;
	}
	public void setFirstname(String firstname) {
		this.firstname = firstname;
	}
	public String getLastname() {
		return lastname;
	}
	public void setLastname(String lastname) {
		this.lastname = lastname;
	}
	public String getAddress() {
		return address;
	}
	public void setAddress(String address) {
		this.address = address;
	}
	
	
	public String getGender() {
		return gender;
	}
	public void setGender(String gender) {
		this.gender = gender;
	}
	/*public String getSkill() {
		return skill;
	}
	public void setSkill(String skill) {
		this.skill = skill;
	}*/
	@Override
	public String toString() {
		return "Employee [id=" + id + ", firstname=" + firstname
				+ ", lastname=" + lastname + ", address=" + address
				+  ", dflag=" + dflag + "]";/*;, skill=" + skill +
*/	}
	
	

}



```


# That's it... you are ready to run

> Right Click on Project > Run As > Run on Server > Select Tomcat Server and click ``finish``

### Note

> In ``spring-web-servlet.xml`` file prefix ``XXX-servlet.xml`` should be same as servlet-name described in ``web.xml`` file

```XML
<servlet>
	<servlet-name>spring-web</servlet-name>
	<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
	<load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
	<servlet-name>spring-web</servlet-name>
	<url-pattern>/</url-pattern>
</servlet-mapping>
```


## Meta

Pratik Joshi - pratik.joshi7859@gmail.com

Distributed under the GPL V3.0 license. See ``LICENSE`` for more information.
