# Examples

Sample models are available here: [https://github.com/telosys-models](https://github.com/telosys-models)&#x20;

### Driver.entity

```
// Entity Driver
// Defines a person who is able to drive a car
Driver {
   id : long { @Id } ;
   firstName : string { @SizeMax(20) @NotEmpty } ;
   lastName  : string { @SizeMax(20) @NotEmpty } ;
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
  brand  : Brand { @NotNull } ; // 1 Brand
  driver : Driver[] ; // N driver
}
```

