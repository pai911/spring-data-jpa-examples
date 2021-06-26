# spring-data-jpa-examples
Demonstrate how to define JPA Entities for different cases of relationships

# One to One
User -- UserProfile
- Ownning relation is the one containing the foreign key (UserProfile)
- UserProfile (Owner) --> User (@OneToOne, Eager)
- User --> UserProfile (@OneToOne, Eager)

https://stackoverflow.com/questions/21499580/why-lazy-loading-not-working-in-one-to-one-association/21499719
https://stackoverflow.com/questions/43754400/hibernate-onetoone-forced-to-chose-between-optional-false-or-cascade/47666344#47666344
https://stackoverflow.com/questions/43678271/hibernate-is-loading-lazy-objects-without-being-asked-for
https://stackoverflow.com/questions/1444227/how-can-i-make-a-jpa-onetoone-relation-lazy
https://stackoverflow.com/questions/63350825/spring-jpa-lazy-loading-onetoone-entities-doesnt-work
https://vladmihalcea.com/the-best-way-to-map-a-onetoone-relationship-with-jpa-and-hibernate/

# One to Many
User -- Post
- Ownning relation is the one containing the foreign key (Post)
- Post (Owner) --> User (@ManyToOne, Eager)
- User --> Post (@OneToMany, Lazy)

# Many to Many (Case 1)
Don't define the bridge table (no additional fields)
Post -- PostTag (Owner) -- Tag
- @ManyToMany + @JoinTable

# Many to Many (Case 2)
Define the bridge table (can define additional fields)
Post -- PostTag (Owner) -- Tag
- Ownning relation is the one containing the foreign key (PostTag)
- Post (@OneToMany) -- PostTag (@ManyToOne)
- Tag (@OneToMany) -- PostTag (@ManyToOne)
