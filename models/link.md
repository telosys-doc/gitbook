# Link

A **link** is a reference from an entity to another entity. It's a relationship with a cardinality (one to many, many to one, etc).&#x20;

The syntax is similar to that of attributes; \
simply replace the neutral type with the **name of the referenced entity**.&#x20;

To reference a **collection** of entities just add "**\[ ]**" after the entity name.

Examples:

```
department : Department ;     // link = single Department
```

```
items : PurchaseOrderItem[] ; // link = collection of PurchaseOrderItem
```

&#x20;

### Cardinalities

#### "Many To One"

Example with 2 entities "**Employee**" and "**Department**"&#x20;

* a Department can have many Employees
* each **Employee** works in **one Department**

So we have a "**Many-to-One"** relationship from Employee to Department\
**N employees → 1 department**

```
Employee {
  department : Department ;  // Many-to-One due to single reference to Department
}
```

When using a **single reference** to an entity the cardinality is "**Many-to-One**" **by default**.



#### "One To One"

Example with 2 entities "**Employee**" and "**Computer**"

* each Employee is assigned one Computer&#x20;
*  each Computer is assigned to one Employee

So we have a "**One-To-One**" relationship between Employee and Computer

```
Employee {
  computer : Computer { @OneToOne } ; // One-to-One due to single ref and "@OneToOne"
}
```

To indicate that this is a "**one-to-one**" relationship, add the annotation **@OneToOne**&#x20;



#### "One To Many"

Example with 2 entities "**PurchaseOrder**" and "**PurchaseOrderItem**"

* each PurchaseOrder has many PurchaseOrderItem
*  each PurchaseOrderItem is assigned to a single PurchaseOrder&#x20;

So we have a "**One-to-Many"** relationship from PurchaseOrder to PurchaseOrderItem&#x20;

```
PurchaseOrder {
  items : PurchaseOrderItem[] ;  
  // One-to-Many due to "[ ]" (many references)
  // mappedBy will be inferred from the owning side if possible
}
```

```
PurchaseOrder {
  items : PurchaseOrderItem[] { @MappedBy(purchaseOrder) } ;
  // One-to-Many due to "[ ]" (many references)
  // mappedBy explicitly defined
}
```



#### "Many To Many"

Example with 2 entities "**Employee**" and "**Skill**"

* an Employee can have many Skills
* a Skill can be assigned to several Employees

So we have a "**Many-toMany**" relationship between Employee  and Skill&#x20;

In a relational database, a "**join table**" (association table) is required to represent a Many-to-Many relationship. In the Telosys model, this "join table" is materialized by a "**join entity**" (a special entity that allows the "join table" to be represented in the model).&#x20;

```
@JoinEntity  // marks this entity as a "join entity" (just for relationship)
EmpSkill { 
  empId   : int  { @Id @FK(Employee) @DbName(EMP_ID) }; // 1rst Foreign Key
  skillId : long { @Id @FK(Skill) @DbName(SKILL_ID)};   // 2nd Foreign Key
}
```

```
Employee {
  skills : Skill[] { @ManyToMany @LinkByJoinEntity(EmpSkill) };
  // use @LinkByJoinEntity on the "owning-side" of the relationship 
}
```

```
Skill {
  employees : Employee[] { @ManyToMany @MappedBy(skills) @FetchTypeEager }; 
  // use @MappedBy on the "inverse-side" of the relationship (like with JPA)
}
```



