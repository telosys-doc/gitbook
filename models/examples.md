# Examples

Sample models are available here: [https://github.com/telosys-models](https://github.com/telosys-models)&#x20;

Below some entities examples:

### Driver.entity

```
// Entity Driver
// Defines a person who is able to drive a car
Driver {
   id : long { @Id } ;
   firstName : string { @MaxLen(20) @NotEmpty } ;
   lastName  : string { @MaxLen(20) @NotEmpty } ;
   birthDate : date { @Past };
   certified : boolean ;
}
```

### Car.entity

```
// Entity Car
// with autoincremented id
Car {
  // basic attributes
  id    : int { @Id @AutoIncremented } ; 
  name  : string { @SizeMax(40) } ;
  year  : short  { @Min(1900) @Max(2020) } ;
  price : float  { @Min(500)  @Max(99999) };
  
  // links (references to other entities)
  brand  : Brand ; // 1 Brand (ManyToOne)
  driver : Driver[] ; // N Driver (OneToMany)
}
```

