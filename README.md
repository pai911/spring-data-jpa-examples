# spring-data-jpa-examples
Demonstrate how to define JPA Entities for different cases of relationships

# One to One
User -- UserProfile
- Ownning relation is the one containing the foreign key (UserProfile)
- UserProfile (Owner) --> User (@OneToOne, Eager)
- User --> UserProfile (@OneToOne, Eager)

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
