
🔗 JPA/Hibernate Entity Relationship Mapping Table

| Annotation             | Relationship Type  | Description                                                                 | Common Attributes                                | Default Fetch Type | Example Usage                                |
| ---------------------- | ------------------ | --------------------------------------------------------------------------- | ------------------------------------------------ | ------------------ | -------------------------------------------- |
| `@OneToOne`            | One-to-One         | Each entity has one related entity                                          | `mappedBy`, `cascade`, `fetch`, `optional`       | `EAGER`            | `@OneToOne @JoinColumn(name = "profile_id")` |
| `@OneToMany`           | One-to-Many        | One entity has a collection of related entities                             | `mappedBy`, `cascade`, `fetch`, `orphanRemoval`  | `LAZY`             | `@OneToMany(mappedBy = "department")`        |
| `@ManyToOne`           | Many-to-One        | Many entities are associated with one entity                                | `cascade`, `fetch`, `optional`                   | `EAGER`            | `@ManyToOne @JoinColumn(name = "dept_id")`   |
| `@ManyToMany`          | Many-to-Many       | Many entities relate to many others (via join table)                        | `mappedBy`, `cascade`, `fetch`                   | `LAZY`             | `@ManyToMany(mappedBy = "courses")`          |
| `@JoinColumn`          | FK Specification   | Specifies the foreign key column for `@OneToOne` or `@ManyToOne`            | `name`, `nullable`, `referencedColumnName`       | —                  | `@JoinColumn(name = "user_id")`              |
| `@JoinTable`           | Join Table Mapping | Defines intermediate join table for `@ManyToMany` or unidirectional mapping | `name`, `joinColumns`, `inverseJoinColumns`      | —                  | `@JoinTable(name = "student_course", ...)`   |
| `mappedBy` (attribute) | Bidirectional Link | Declares non-owning side of a bidirectional relationship                    | Used in `@OneToOne`, `@OneToMany`, `@ManyToMany` | —                  | `@OneToMany(mappedBy = "user")`              |


**Owning Side:** The owning side of the relationship is the one that manages the foreign key in the database. This side controls the relationship and has the mapping annotation that specifies how the relationship is stored (e.g., @JoinColumn, @ManyToOne, etc.).

**Non-Owning Side:** The non-owning side of the relationship doesn't manage the foreign key. It's simply a reference to the owning side of the relationship. This side can still reference the owning side, but it does not have the control over how the relationship is persisted or updated in the database.



