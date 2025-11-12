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

#### "Many To One" link&#x20;

Example with 2 entities "**Employee**" and "**Department**"&#x20;

* a Department can have many Employees
* each **Employee** works in **one Department**\
  so we have a "**Many-to-One"** relationship from Employee to Department\
  **N employees → 1 department**

```
Employee {
  department : Department ;  // Many-to-One due to single reference to Department
}
```



#### "One To One" link&#x20;

Example with 2 entities "**Employee**" and "**Computer**"

* each Employee is assigned one Computer&#x20;
*  each Computer is assigned to one Employee

So we have a "One-To-One" relationship between Employee and Computer

```
Employee {
  computer : Computer { @OneToOne } ; // One-to-One due to single ref and "@OneToOne"
}
```

To indicate that this is a "**one-to-one**" relationship, add the annotation **@OneToOne**&#x20;



#### "One To Many" link



```
PurchaseOrder {
  items : PurchaseOrderItem[] ;  // One-to-Many due to "[ ]" (many references)
}
```



#### "Many To Many" link



```
Employee {
  skills : Skill[] { @ManyToMany @LinkByJoinEntity(EmpSkill) };
}
```



