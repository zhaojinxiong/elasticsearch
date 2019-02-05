### 集成Thymeleaf 及基本用法。
1. what? why? how?
2. jsp framemark Thymeleaf 
3. Thymeleaf(语法更接近html)
4. 集成BootStrap Jquery

<properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>

    <!-- 使用自定义ES 版本 -->
    <elasticsearch.version>5.6.1</elasticsearch.version>

    <!-- thymeleaf 覆盖parent 选择自己的版本 -->
    <thymeleaf.version>3.0.3.RELEASE</thymeleaf.version>
    <thymeleaf-layout-dialect.version>2.1.1</thymeleaf-layout-dialect.version>
    <thymeleaf-extras-springsecurity4.version>3.0.2.RELEASE</thymeleaf-extras-springsecurity4.version>
</properties>


<!-- 前端模板 thymeleaf 依赖 -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>

<!-- https://mvnrepository.com/artifact/org.thymeleaf/thymeleaf -->
<dependency>
    <groupId>org.thymeleaf</groupId>
    <artifactId>thymeleaf</artifactId>
    <version>${thymeleaf.version}</version>
</dependency>

<dependency>
    <groupId>org.thymeleaf</groupId>
    <artifactId>thymeleaf-spring4</artifactId>
    <version>3.0.2.RELEASE</version>
</dependency>


<!-- dev-tools -->
<!-- spring-boot 自带的热加载开发工具 -->