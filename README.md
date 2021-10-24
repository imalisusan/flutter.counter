# counter

A counter app to learn Flutter Bloc Concepts

## Flutter Bloc Crash Course Short Notes
For every interaction, the app should be in a different state. Bloc helps in managing these states
 
# Advantages
1. Understand easily what's happening inside your app
2. More structured code, easier to maintain and test
3. Know and understand every state of your app
4. Work on a single, stable, popular and effective Bloc codebase
 
Bloc core concepts
 Async function- generates a synchronous data
 Await- wait for a process to finish
 Listen- wait for incoming data
 
Cubit is a minimal version of a Bloc. Bloc extends cubit.
Cubit is a special Kind of a stream component based on some functions which are called from the UI. The functions rebuild the UI by emitting different states on a stream. Cubic functions are not part of a stream.  They are simply a pre-baked list of what the Kindle can do. A stream of states is the only stream in cubit.
Bloc emits a stream of states. It also receives a stream of events.
When to use Bloc/Cubit?
There should be a Bloc or cubit component for every feature of your app. 
 
# Flutter Bloc Components
Every concept is a widget.  Widgets are classes which have their own attributes and constructors. Bloc will provide a single instance of a Bloc to the subtree below.  BlocProvider widget creates and provides a Bloc to all its children. It is also known as a dependency injection widget.  It takes the build context as an argument and returns only one instance of the Bloc.  Context is the context in which a specific widget is built. By default, BlocProvider creates the Bloc lazily.  To override it, set the lazy attribute to false.
 
BlocProvider handles the closing part of Blocs automatically.
 
BlocProvider.value- Provides the only instance of Bloc a to the new portion of the tree.
 
Since the only instance of blocA was created where the BlocProvider, it will get automatically closed by the BlocProvider.  Providing it to the second page (using blocprovider.value) won't close the only instance of the Bloc on the second page gets destroyed. This is because the instance may still be needed in the page above, in the ancestor tree. However, the Instance will be closed when needed because of the way it was created in the first place- by using BlocProvider
 
 You can access the current state of a cubit by using the state keyword.
 
# Bloc Builder
A widget that helps rebuilding the you are based on the Bloc state changes.  Reveals the UI every single time A new state is emitted.  Rebuilding a large chunk of the UI may require a lot of time to compute; that's why you should rebuild only the widgets being changed. 
The Builder function can be called multiple times due to how the Flutter engine works. Return widgets based on the bloc’s State.  The Builder function must be a pure function.  A function is a function where the return value depends only on the function’s parameters and nothing more.
 
buildwhen(previousstate, state)
 
BlocProvider- creates and provides the only instance of a bloc to the subtree.
BlocBuilder- rebuilds the UI for every new state coming from the bloc
BlocListener- this listener function is called only once per state. Optional listenWhen function
BlocConsumer- combines both BlocBuilder and BlocListener into a single widget.
RepositoryProvider- provides a unique instance of a repository
MultiBlocProvider, MultiBlocLister,MultiRepositoryProvider
 
# Bloc Architecture
Bloc is a design pattern, a state management library and an architectural pattern.
Almost all apps retrieve data from the internet. We need to link our bloc-based Flutter app with the outer data layer. The data layer consists of repositories, data providers and the models. The model data shouldn’t be the same as the data provided to the weather API. The data provider is an API for your app. The different methods request data straight from the internet. 
Blocs can communicate with each other.
 
# Bloc Testing
Pros vs Cons- deciding whether its worth choosing testing for its advantages over its disadvantages. Learn and understand the structure.
In dart, two instances of the same class aren’t equal, even though they are the same. Use the equitable library.
Pub run test- runs tests.
 
