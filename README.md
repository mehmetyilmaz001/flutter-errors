# flutter-errors

- “setState() or markNeedsBuild() called during build. This Overlay widget cannot be marked as needing to build because the framework is      already in the process of building widgets…“
  - You ensure that buid is completed. 
     You can use (in initState());
      - WidgetsBinding.instance.addPostFrameCallback((_){
          showDialog(
            context: context, 
            ...
          );
        });
       - Future.microtask(() => print("microtask"))
  
- An InputDecorator, which is typically created by a TextField, cannot have an unbounded width
  - Solution: Put TextFormField into a Expanded or Contaniner (width with)
  
- Got TLS error trying to find package on Windows
  - Your organization network may block some connections. Try another wifi / network
  
- Duplicate GlobalKeys detected in widget tree.
  - It likes a hot reload bug. Just restart debugging 

- Make sure to implement the onDismissed handler and to immediately remove the Dismissible widget from the application once that handler has fired.
  - Be sure that item is properly removed from the list. If dismissible item stays still in the list the dismissble widget    throws this error

