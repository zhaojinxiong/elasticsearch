@Configuration
@EnableJpaRepositories(basePackages = "com.coder.es_house.repository")
@EnableTransactionManagement
public class JPAConfig {
    @Bean
    @ConfigurationProperties(prefix = "spring.datasource")
    public DataSource dataSource() {
        return DataSourceBuilder.create().build();
    }

    @Bean
    public LocalContainerEntityManagerFactoryBean entityManagerFactoryBean() {
        HibernateJpaVendorAdapter jpaVendorAdapter = new HibernateJpaVendorAdapter();
        jpaVendorAdapter.setGenerateDdl(false);
        LocalContainerEntityManagerFactoryBean entityManagerFactory = new LocalContainerEntityManagerFactoryBean();

        entityManagerFactory.setDataSource(dataSource());
        entityManagerFactory.setJpaVendorAdapter(jpaVendorAdapter);
        entityManagerFactory.setPackagesToScan("com.coder.es_house.entity");
        return entityManagerFactory;
    }

    @Bean
    public PlatformTransactionManager transactionManager(EntityManagerFactory entityManagerFactory){
        JpaTransactionManager transactionManager = new JpaTransactionManager();
        transactionManager.setEntityManagerFactory(entityManagerFactory);
        return transactionManager;
    }
}


### JPA 
> JPA(java Persistence API) 是用于管理Java EE 和 Java SE 环境中的持久化，以及对象/关系映射的java API 
    +  JPA 核心概念
       +  实体 POJO 
          +  实体表示关系数据库中的表
          +  每个实体实例对应于该表中的行。
          +  类必须用javax.persistence.Entity 注解.
          +  类必须有一个public或protected的无参数的构造函数
          +  实体实例被当作值以分离对象方式进行传递，则该类必须实现Serializable接口
          +  唯一的对象标识符：简单主键 复合主键 （javax.persistence.Embeddedid）
       +  关系
          +  一对一 @OneToOne
          +  一对多 @OneToMany
          +  多对一 @ManyToOne
          +  多对多 @ManyToMany
       +  EntityManager 接口
          +  定义用于与持久化上下文进行交互的方法。
          +  创建和删除持久化实体实例，通过实体的主键查找实体。
          +  允许在实体上运行查询。


### Spring Data JPA 用法介绍
    + 什么是Spring Data JPA
      + 是更大的Spring  Data 家族的一部分
      + 对基于JPA的数据访问层的增强支持。
      + 更容易构建基于使用Spring 数据访问技术栈的应用程序。
    + Spring Data JPA 常用接口
      + CrudRepository 
      + PagingAndSortingRepository
    + Spring Data JPA 自定义接口
      + 根据方法名创建查询

### Spring Data JPA Hibernate 与 Spring Boot 集成
    +


