# Examples

### Driver.entity

```text
// Entity Driver
// Defines a person who is able to drive a car
Driver {
   id : long { @Id } ;
   firstName : string { @SizeMax(20), @NotEmpty } ;
   lastName  : string { @SizeMax(20), @NotEmpty } ;
   birthDate : date { @Past };
   certified : boolean ;
}
```

### Car.entity

```text
// Entity Car
// with autoincremented id
Car {
  // basic types
  id : int { @Id, @AutoIncremented } ; 
  name : string { @SizeMax(40) } ;
  year : short { @Min(1900), @Max(2020) } ;
  price : float { @Min(500), @Max(99999) };
  // references to other entities :
  brand : Brand { @NotNull } ; // 1 Brand
  driver : Driver[] ; // N driver
}
```


