# Frontend Architecture: 
#### intuition from working in Vue.

## Three Data Models
### Application Data
  These types are optimized for the performance of application logic.
  They trade space for time without pointlessly repeating data.
  Protocol for all within-app behaviors.

### User Interface
  These types are optimized for display based on component criteria.
  They are mapped directly from slices of application data. 
  
### Endpoint Rules
  These types are descriptions of externally-enforced criteria.
  Requests are mapped directly from slices of application data.
  Responses map directly to slices of application data.

## Coordinating Models
### Multi-store Libraries
 - [Pinia](https://pinia.vuejs.org/) for Vue
 - [Zustand](https://github.com/pmndrs/zustand): React

These libraries allow you to have many stores, and to call one store from within another.
A store can handle a particular slice of data, and other stores can import and rely on it.
That property allows for composable state management focused high-resolution criteria.

### Separating Concerns
  Each data model lives in its own ecosystem of stores.
  The application model is the most unified, representing entire units of big-picture logic.
  The UI model is housed across smaller stores tied directly to components.
  The endpoint model is made of individual wrappers, and coordinated call patterns.
