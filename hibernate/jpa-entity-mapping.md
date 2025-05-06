
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
