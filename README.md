# uaiCriteria 
## How can JPA criteria became easier?

### BuildStatus ---> [![Build Status](https://travis-ci.org/uaihebert/uaicriteria.svg?branch=master)](https://travis-ci.org/uaihebert/uaicriteria)

> Yes, your JPA Criteria can be easy. All you need to do is to add uaiCriteria in your implementation. 
>
>Imagine that you want to run the following JPQL: 
>
```sql 
select p from Person p 
``` 
>
> If you want do write the JPQL above using only the JPA native Criteira, you should do something like:
>
```java
 CriteriaQuery<Person> criteriaQuery = criteriaBuilder.createQuery(Person.class);
 Root<Person> root = criteriaQuery.from(Person.class);
 criteriaQuery.select(root);
 TypedQuery<Person> query = entityManager.createQuery(criteriaQuery);
 query.getResultList();
```
> 
> With uaiCriteria you could run like this:
>
```java
UaiCriteria<Person> easyCriteria = UaiCriteriaFactory.createQueryCriteria(entityManager, Person.class);
uaiCriteria.getResultList();
```
> To create a code like the code above, add the maven dependency below:
```xml
<dependency>
    <groupId>uaihebert.com</groupId>
    <artifactId>EasyCriteria</artifactId>
    <version>3.0.0</version>
</dependency>
```
>
> Now, criteria is easy to use! ;) 


You have the following mvn commands available:

* if you want to build the project run: mvn clean package
* if you want to test the project run: mvn clean test
* if you want to generate the cobertura report use: mvn cobertura:clean cobertura:cobertura
    * the generated report can be found at: ``<uaiCriteria_FOLDER>``/target/site/cobertura/index.html
