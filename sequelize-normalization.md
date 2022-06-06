# Reading Day5

## [Home Page](/README.md) 

## sequelize-normalization

To do this, Sequelize provides four types of associations that should be combined to create them:

- The HasOne association

- The BelongsTo association

- The HasMany association

- The BelongsToMany association


The A.hasOne(B) association means that a One-To-One relationship exists between A and B, with the foreign key being defined in the target model (B).

The A.belongsTo(B) association means that a One-To-One relationship exists between A and B, with the foreign key being defined in the source model (A).

The A.hasMany(B) association means that a One-To-Many relationship exists between A and B, with the foreign key being defined in the target model (B).

These three calls will cause Sequelize to automatically add foreign keys to the appropriate models (unless they are already present).

The A.belongsToMany(B, { through: 'C' }) association means that a Many-To-Many relationship exists between A and B, using table C as junction table, which will have the foreign keys (aId and bId, for example). Sequelize will automatically create this model C (unless it already exists) and define the appropriate foreign keys on it.


* To create a One-To-One relationship, the `hasOne` and `belongsTo` associations are used together;

* To create a One-To-Many relationship, the `hasMany` and `belongsTo` associations are used together;

* To create a Many-To-Many relationship, two `belongsToMany` calls are used together

## Fetching associations - Eager Loading vs Lazy Loading

The concepts of Eager Loading and Lazy Loading are fundamental to understand how fetching associations work in Sequelize. Lazy Loading refers to the technique of fetching the associated data only when you really want it; Eager Loading, on the other hand, refers to the technique of fetching everything at once, since the beginning, with a larger query.

## Why associations are defined in pairs?

usually associations in Sequelize are defined in pairs:

- To create a One-To-One relationship, the hasOne and belongsTo associations are used together;

- To create a One-To-Many relationship, the hasMany and belongsTo associations are used together;

- To create a Many-To-Many relationship, two belongsToMany calls are used together.

When a Sequelize association is defined between two models, only the source model knows about it. So, for example, when using Foo.hasOne(Bar) (so Foo is the source model and Bar is the target model), only Foo knows about the existence of this association. This is why in this case, as shown above, Foo instances gain the methods `getBar()`, `setBar()` and `createBar()`, while on the other hand Bar instances get nothing.

Similarly, for Foo.hasOne(Bar), since Foo knows about the relationship, we can perform eager loading as in `Foo.findOne({ include: Bar })`, but we can't do `Bar.findOne({ include: Foo })`.

Therefore, to bring full power to Sequelize usage, we usually setup the relationship in pairs, so that both models get to know about it.