# Adding a new model in the store:
1. Add a model.ts which defines the data model of the new store object.
2. Add a model.actions.ts. This file has all the actions defined in it.
3. Add a model.reducers.ts. This file has:
- the entity adapter (from @ngrx/entity)
- state model
- state initial object
- reducer that is specific to this model
- entity.getSelectors that returns all the selectors for this model
