# LearnSwiftUI
Start to learn SwiftUI
Hi, everyone.
I'm Jacob Xiao and I'll be joined later by Kyle Macomber.
We're so excited to show you SwiftUI, a revolutionary new way to build better apps faster.
We think the best way to learn about Swift UI is to see it in action by building an app.
Using SwiftUI feels like magic, but to make it clear that I don't have anything up my sleeves, I want to go through the entire process of creating an app in SwiftUI starting from scratch.
So what kind of an app are we going to make? Well, let me set the stage for you.
Anybody here hate meetings? Yeah? Well, so do we.
But Kyle and I have found something that makes meetings more bearable, and that's having them in amazing, fancy conference rooms.
So we've been making a list of all of the best conference rooms we can find and we want to make an app for it.
So let's dive in.
Okay.
I'll start by creating a new project.
And we'll call it Rooms.
And I'll make sure that Use SwiftUI is checked.
Now Xcode has started us off with a view, with the view that we can use to start building our UI.
Our code is over here on the left.
And on the right is the Canvas.
And if you're familiar with Interface Builder or Storyboards, you may think that there's nothing new here.
Some code on one side and a visual Canvas on the other, right? Well, there's a very important difference.
With Storyboards, you need to choose between the benefits of using a visual editor, or the benefits of creating your UI in code.
And if you choose one and change your mind later, then you have to start all over again.
But with SwiftUI, that problem is gone.
Now your view definition is always Swift's code and you can always choose to edit the code directly or to use the visual editor.
And you can always go back and forth.
So if we select something in the Canvas, then that selection is reflected in the code as well.
And if you change something in the code, then that change is reflected in the Canvas as well.
They work together seamlessly.
So let me tell you a little more about how it works.
The Canvas shows us previews of our view code.
And it even helps us edit and learn about that code.
Xcode shows these previews by compiling our real code and running it to generate a result.
But one of my favorite things about previews is that they're also created using SwiftUI code.
In this case, the code right here.
And later on, we'll see how that gives us a lot of power to customize our previews.
Now our app is going to show a list of conference rooms, so let's make the cell for our list.
I'm going to add another piece of text under this one to show more detail about each room.
And I'm going to add it by just dragging it out onto my Canvas.
And Xcode even shows me what will happen when I place it at different locations.
Now when I drop it in, the preview updates to show my new text, but even better, Xcode has actually edited my code to add that text.
Xcode has embedded these views into a Vstack to get the layout that I want.
Now a Vstack or vertical stack is one of the common layout elements in SwiftUI.
It lets you stack views vertically.
And there's also an Hstack that stacks views horizontally.
And these stacks are containers.
I can place any views that I want inside of them.
Now I'm going to replace this placeholder that Xcode has given me with some more information about the room.
We'll show the number of people that it can hold.
And for now, let's just use a hard-coded value.
Next, let's add an image next to our text.
I can make edits in the code just as easily as in the editor.
So let's embed our view in an Hstack.
I can Command-click on my view and choose Embed an H Stack.
And Xcode has updated the code to do just that.
Now I can add an image next to my Vstack.
We'll add some assets in a bit, but for now I'll just use an SF symbol image to get something up and running.
SF symbols are new in iOS 13.
They're a rich set of Apple-provided images that you can use in your app.
And already we have a basic version of our cell.
Now, I'll use the Canvas to style the cell the way I want.
I can Command-click on my stack and choose Inspect to see some of the properties that I can change for this stack.
I'm going to set its alignment to be leading.
And, once again, Xcode has updated my code to make that change.
Now, I can also Command-click on my text to inspect that as well.
And let's change this to be a smaller font.
I'm going to use sub-headline.
And one of the great things about Xcode modifying my code is it helps me to learn about SwiftUI.
For example, here it's added this code to change the font.
We call these kinds of methods modifiers and they're used in SwiftUI to customize the way your views look or behave.
I'm going to add another modifier in code to set the foreground color to be a secondary color.
Okay.
Now that I have my cell, let's put it into a list.
To do that, I'm going to Command-click on our cell and just choose Convert To List.
This wraps my cell in a list and shows five iterations of it.
It's great to be able to do this so easily.
And this code is all that I need to show a list in my app.
There's no delegates or data sources necessary, just views inside of a list.
Next, let's hook this up to some data.
I'm going to drag in some assets and a model file that I created earlier.
Now my model has a few fields of information that we'll use.
And to use this in a list in SwiftUI, I just need to make this type identifiable.
This lets Lists know which items are coming and going.
And all I need is an ID property which we already have.
Now this model file also includes some test data that I can use for debugging my app.
Now let's go back to our view and let's pass in our data.
I'll add a property for my rooms.
And one of the great things about previews is that they can use their own test data.
So I'll just pass in my test data right here.
Now you may have noticed that this banner appeared above my preview.
When I make larger changes to my types like adding this rooms property to our view, Xcode pauses the previews until I'm ready to have them resume updating.
And I can just click button to resume.
Next, let's use our data to drive the list.
We'll pass in our rooms to the list and then I'll update our text to show the room's name.
And we'll also use the real capacity right here in our text.
And now that we have real images, let's also use our Rooms thumbnail for the image.
Great.
And you may have noticed the subtle change that happened to our list when we did this.
When we started, our cells were the standard 44 points tall.
But when we changed to these larger images, the cells automatically expanded to make sure those images fit without any extra work.
It's pretty cool.
And now that I have these images in context, they look a little bit sharp.
So let's add a corner radius to our image using another modifier.
And if you're not sure about what modifiers are available, you can view and filter a list of them right here in the library.
Let's find Corner Radius and we'll just drag it onto our image.
Then we can tweak the values.
That looks a little bit too big.
Great.
And now that our cells and our lists are looking good, the next thing that we need is to be able to tap on a cell to see more details.
To support this, let's wrap our list in a navigation view.
A navigation view shows a navigation bar and also has a stack to push views onto.
Let's also set a navigation bar title and we'll just use some text that says Rooms to show Rooms in our navigation bar.
Now let's set up our cell to push onto this stack.
To do that, I'll wrap our cells content in a Navigation button.
A Navigation button takes a destination which is a view that will push onto the stack.
And to start with, we'll just use some text that shows the room's name.
Then we'll put all of our cell's content inside of that navigation button and we're ready to go.
And notice that our UI has updated to automatically show these UI indicators.
SwiftUI handles details like this for me automatically so that my UI automatically looks right by default.
Now let's also check that the cell behaves correctly.
I can just click on this play button in my preview, which takes me into Live Mode.
And when I do this, Xcode is compiling my code, sending it over to the Simulator, running it for me and showing the result of all of that right here in the Canvas, which means I can interact with my view.
So I can tap on a cell to make sure that everything pushes and pops as I expect.
And if I swipe to pop, you'll notice an advanced behavior that SwiftUI has given me automatically.
Our cells stay highlighted, and as I swipe, they are interactively un-highlight it without us doing any extra work.
Okay, so we've got our list and it's working with its cells.
But this view code is a little bit large now.
And I'd really like to factor the cell out to be its own view.
And Xcode helps me do this with one simple operation.
I can just command click on the view that I want and choose Extract Subview.
It's fantastic.
All of my view code gets extracted out down here and I even get to choose the name for my new view.
Let's call it Room Cell.
Thank you.
Now, let's also add a property for our room.
And we'll pass it in right here.
This is a fantastic workflow improvement.
And with SwiftUI, views are really lightweight so you don't have to worry about creating extra views to better encapsulate or separate your logic.
Okay, next let's build our detail view.
I'm going to create a new view and make sure to use the SwiftUI Template.
And let's call this new view Room Detail.
Xcode has automatically given me a new ViewStruct and also the preview code to create it.
Now since I want this detail view to show more information about my room, I'll add a property for the room.
And just like I did before, I'll update my preview code to pass in one of our rooms from their test data.
Then let's build our UI.
We use an image and we'll show the room's image name.
Okay, now we're showing our image but it's a little bit too large for our view.
By default, SwiftUI shows all images at the size of their contents to prevent visual artifacts from scaling the image up or down.
But for photos like this one, we want to be able to resize them down.
And we can use an image-specific modifier called Resizable to do that.
So I'll just drag this onto our view and all right, now it's resizing to fill the size that we have.
But really we want it to maintain this original aspect ratio.
And we can do that with another modifier, this time aspect ratio.
And the aspect ratio modifier lets me choose between .
fill, which expands the image to take up its entire frame, or .
fit, which makes sure the image fits within the frame.
And previews let me really easily see and understand the difference between these different modes.
For now, let's use Fit so we can see the full image.
Now let's go back to our list and update our cell to push our new detail view.
We'll create our Room Detail view and we'll just pass in the current room.
Now I'll switch my preview back into live mode.
And I can tap on my cell to see our image.
But now that I'm previewing it here, I can see that I forgot to set the title in the navigation bar.
So let's go back to our detail view and fix that.
Just like before, I can use the navigation bar title to set our title and we'll pass in our room's name as the title.
But in the preview that I have here, we're only seeing the view itself and I'd really like to be able to quickly verify my change.
Well, since previews have all the power of SwiftUI's views available, we can do just that.
I can set up my preview to be inside of a navigation view using the same code that I would anywhere else.
And now my view's preview is inside of a navigation bar.
And now that I'm seeing it here, this large title looks like a little bit too much for our detail view.
So let's update our navigation bar title to set the display mode to be inline.
Much better.
Now when I'm picking a good conference room, there's one thing that's very important to me.
The room has to have a good table.
I just can't focus on what anyone is saying if the table isn't of the highest quality.
And I can see that there's some kind of table in this room, but I really can't see its details well enough.
But when the image was in Fill, I could see it nice and close.
Look at that wood grain.
So I'd like to be able to change back and forth between Fill to see the details of the room and Fit to see everything at once.
But how do I actually change this aspect ratio's content mode from within my view? Well, to understand how to do this, we really need to know more about how views work in SwiftUI and why.
And so I'm going to invite Kyle to the stage to talk about that.
Kyle?  Well, hello, WWDC.
What does everyone think of SwiftUI so far?  Yeah, I'm pretty excited too.
It's a little magical though.
And so before we go any further, we're going to take a step back and talk about the way views work and why in SwiftUI.
So we left off here implementing Room Detail view.
In SwiftUI, a view is a struct that conforms to the view protocol, rather than a class that inherits from a base class like UI view.
This means your view doesn't inherit any stored properties.
It's allocated on the stack and it's passed by value.
Room Detail just stores a room, so it's the size and weight of a room.
No additional allocation or reference counting overhead.
Behind the scenes, SwiftUI aggressively collapses your view hierarchy into an efficient data structure for rendering.
Because of this, we make liberal use of small single-purpose views in SwiftUI, and you should too.
What I want you to take away from the last couple slides is that views in SwiftUI are incredibly lightweight.
As Jacob said, you should never hesitate to refactor your SwiftUI code because extracting a subview has virtually no runtime overhead.
Yeah, you can clap for that, it's pretty great.
So a view in SwifthUI and a view in a traditional UI framework fulfill the same primary role.
They define a piece of UI.
The view protocol only has a single requirement: a body property, which is, itself, a view.
You build bigger views in SwiftUI by composing together smaller views.
We built Room Detail by composing together image, a view of an image at its native resolution, resizable which opted it into stretch in either dimension; and aspect ratio, a view that proportionally scales its child.
The rendering of any view you build is just the rendering of its body.
So if you set a break point and the debugger stops there, it means the framework has decided it needs a fresh rendering of your view.
Tada.
All right.
So the framework knows when to fetch a new rendering of a view because in addition to defining a piece of UI, in SwiftUI, a view defines its dependencies.
Let's extend Room Detail to allow the user to toggle between fitting into and filling up the available space so Jacob can get a good look at that wood grain.
So, the first thing we'll need is a property, but it's a special property.
It's a state property and it says whether or not the image is zoomed.
When SwiftUI sees a view with a state variable, it allocates storage for that variable on the view's behalf.
In this Memory diagram, the green is your app's memory, and purple is memory SwiftUI is managing.
And so this value of the zoom variable, we got you covered.
So if you decide to fill or fit based on that variable, then we've got a view that renders like this when it's zoomed and like this when it isn't.
So, now, all we need is a tapAction to toggle back and forth between the two states.
And then on tap, the image will zoom to Fill and shrink to Fit.
So what actually is happening when we tap here? Well, one of the special properties of state variables is that SwiftUI can observe when they're read and written.
Because SwiftUI knows that Zoom here was read in body, it knows that the view's rendering depends on it, which means when the variable changes, the framework is going to ask for body again using the new state value.
So it can refresh the rendering this time with a different content mode.
So, traditional UI frameworks don't distinguish between state variables and plain old properties.
But I've found this distinction to be incredibly clarifying.
In SwiftUI, every possible state your UI might find itself in, the offset of a scroll view, the highlightedness of a button, the contents of a navigation stack.
It's derived from an authoritative piece of data, often called a Source of Truth.
Collectively, your state variables and your model constitute your Source of Truth for your entire application.
Earlier, I mentioned that this call to aspect ratio makes a view.
Its definition looks something like this, where content mode is a plain old Swift property.
You can neatly classify every property as either a source of truth or a derived value.
The Zoom state variable is a Source of Truth.
The Content Mode property is derived from it.
Recall SwiftUI can observe when state variables are read and written.
So when one changes, it knows which renderings to refresh.
The framework refreshes the rendering by asking for a new body, making a new aspect ratio view from scratch, thereby overriding the Content Mode and any other stored properties.
This is the mechanism by which all derived values in SwiftUI are kept up-to-date.
So we've seen how we can declare a Source of Truth using a state variable, and that every plain old property is a derived value.
We're not going to see an example in this talk, but Swift gives you a tool called Binding, which is great for passing read/write derived values.
And technically any constant can serve as a perfectly good read-only Source of Truth as we saw with the test data driving our previews.
Now there's one more I want to call out, and I mentioned a second ago that collectively your state variables and your model constitute the Source of Truth for your entire app.
And so we have this bindable object protocol Jacob used earlier to teach SwiftUI about how to observe changes from our model.
This might be a lot really quickly, and so we have an entire talk later this week dedicated to developing your intuition about these different flow primitives.
All right, let's step back and take stock.
This is really different from what you do in a traditional life framework where the views themselves persist and you try your hardest to keep them all up to date.
You may not think about it this way when you use a traditional UI framework, but every time a view reads a piece of data, it's creating an implicit dependency.
It's a dependency because when that data changes, the view needs to update to reflect the new value.
And when it fails to, that's a bug.
SwiftUI automatically manages dependencies on your behalf by recomputing the appropriate derived values so this never happens again.
Of course, we don't just manage a single dependency at a time in our apps.
Our apps are big.
They're complicated.
When it comes to how much you have to hold in your head and how easy it is to make a mistake, the way we manually manage dependencies today, it's really hard.
Despite my best efforts, every update to every app I've ever shipped has had UI bugs.
Every one of these lines is a dependency.
And it's just the start.
The thing I find the hardest about managing the complexity of my views is dealing with all the possible orders the different callbacks can get called in.
So here's an old version of the room detail view that was implemented in UIKit.
It had the same features as the one we've seen so far has, but it had one more.
Every once in a while, when we zoom in on a conference room image, it was too blurry to make out the wood grain on the table.
And so we decided to add a special feature using neural networks and machine learning so we could tap to enhance the image on a background thread and thus choose the right conference room.
All right, yeah.
Over-engineering, right? So there's only one problem with this feature and that's it had a bug.
We got a report of a stray activity indicator that never stops spinning.
How'd this happen? Well, it turns out if the events fired in a specific order, we forgot to clean up that activity indicator.
In this case, if the user zoomed out and tapped the enhance button as it was animating away, the activity indicator would get stuck.
These kinds of mistakes are easy to make when you mutate your subviews directly from event handler callbacks rather than updating your Source of Truth and deriving your UI from that.
Now we make this mistake because when we're coding this code, it's really easy to only think about the happy path.
Those are the ones that come easily to mind.
And it's really easy to overlook the unhappy ones that don't.
The problem is that as the number of possible events our view can respond to grows, the number of unhappy paths explodes.
Assume you get all four of these events, how many different possible orders are there that they could come in? Well, there's actually 24 different orders for any four events.
And in practice, it's even worse than that because every event can come in more than one time.
Say for example a user is mashing the enhance button.
The challenge of managing this should be familiar to anyone who's ever implemented an interruptable animation where the completion handler can come in at a really unexpected time.
If I could tell myself from five years ago anything about my job, it would be that UI programming is really hard.
Like log-free concurrency hard.
How many of you have written multi-threaded code? Probably all 2,000 of you, yeah.
So no one pretends that's easy.
It's taken me months to shake out all the bugs in some of my multi-threaded code, and even then I wasn't 100% confident in its correctness.
A lot of UI code is actually just like that, only instead of a crash, your view ends up in the wrong place, or it's missing.
This is because race conditions and UI inconsistencies share the same underlying source of complexity.
These easy-to-overlook orderings.
Many of the views we all work on have way more than four events.
You know, like model notifications, delegate methods, target actions, completion handlers.
They're all events.
A view with 12 would roughly equate to 12 factorial possible orderings.
That's almost half a billion.
We've all worked on views with 12 event handlers.
So you can only fit so much in your head at a time.
Yeah.
This dotted line is one of the views in your app.
What do people think the difference between those two dots is? Anyone? Those are the bugs, yes.
So as we add features, the number of possible orderings we have to think of increases exponentially.
And the chance we overlook one -- it's the same.
It's inevitable.
So I imagine many of you instinctively have reached for a way to handle this complexity in UIKit or AppKit when you program today, which is to collect all your view update code in a single method.
And then from these event handler callbacks, you call that one method.
It's a really great way for the complexity to not explode on you.
Well, SwiftUI was heavily inspired by this best practice.
When you are trying to implement a view this way in UI today, there's all these tricky cases you need to think about like adding or removing a subview from the view hierarchy, or pushing and popping off the navigation stack.
Or performing updates to a table view.
I was never able to figure out all of those cases all on my own.
Well, we've spent all the time and done all the work and we've codified this best practice into SwiftUI on your behalf.
The view protocol only has a single requirement: body.
A single entry point that the framework calls.
That means there's only one possible order it can ever get called in.
Because of this pattern of simply fetching new views for the parts of the UI that changed, SwiftUI scales with your brain, virtually eliminating UI inconsistencies.
All right.
Let's get back to the demo and finish the Room Detail view.
Jacob?  Okay, let's finish this app.
Now, we know how to set up our view to zoom in.
We'll add a state property.
And we'll call it Zoomed and we'll default it to false.
Then in our aspect ratio we'll use the Zoomed property to change between Fill when we're zoomed and Fit otherwise.
And finally, we'll add our tapAction to toggle that Zoomed property.
Now let's try it out in Live Mode.
Great, we can switch between these two different modes.
But there's something missing here.
Does anybody see it? That's right, it needs an animation.
And with SwiftUI, animation's really easy to add.
I can just wrap my change in a call to WithAnimation.
And now my change is animated.
And not only that, the animation is fully interactive and interruptible so I can always change between the different states and it always ends up in the right place.
Yeah, it's great.
Now I would add the Enhance button next, but it turns out that the way Kyle trained the model, it only ever worked on that one image that he showed.
So I'm going to add something more useful.
One of our coworkers is in London so we often want to know which rooms have video conferencing.
So let's show an icon for that on top of our detail view.
I can use a Zstack to show views stacked on top of each other.
So I'll put our existing image inside of that Zstack and then I'll add another image to show an icon for whether the room has video or not.
I'll just use a symbol image and we'll use Video.
fill.
Okay, we have our icon here, but it's a little bit small.
But symbol images automatically use the current font to size themselves, so I can easily change to a larger font with a modifier.
We'll just drag this into our code and apply it to the image.
And Title sounds good.
Now we've got our larger image.
Next, I want this image to be in the top-left.
So let's set our Zstack's alignment to be topLeading.
Okay.
Next let's add some padding so that this is not up against the edge here.
Again, we can use a modifier to do this.
And we'll just drag it in onto our system image.
And All Edges seems like a good choice here.
Okay, this is close, but I really want to have this icon all the way at the top of our view area.
And we can get our video icon there by putting our room image inside of a flexible frame.
The frame will stretch to fill the whole screen.
And when it has extra space, it will center its contents inside of it.
This means that our room image will still be at the right place.
So I'll add our flexible frame to our image.
And we'll use a minimum width of zero and a max width of infinity.
And we'll do the same thing for our height.
There we go.
And if you're curious to learn more about how layout works in SwiftUI, check out the Building Custom Views in SwiftUI session.
Now we have our icon.
But we only want it to appear when a room has video conferencing.
So how do we do that? Well, the declarative syntax that we're using makes that really easy.
We can just use an if.
So I'll add an if and we'll check whether our room has video.
And we'll only show our image when that's true.
Now we can check if this is working by changing our preview data to a room that doesn't have video, which is nice.
But even better, we can actually set up our previews to show multiple versions of our views at once.
To do that, I'm just going to embed this view inside of a group.
And now I can have multiple views here.
So let's create a second version using different test data.
Now we have one version of our view with video conferencing, and another version without.
Now let's go back to live mode.
Now when I'm in the Zoom state, having that icon on top of my image is a little distracting.
So let's update it to also disappear when we're zoomed.
We can do that just by updating our condition.
Now the icon automatically shows and hides as we zoom in and out.
But even better, it animates, fading in and out.
And we can also customize that animation behavior by setting it to a different transition.
So let's try .
move and we'll use the leading edge.
Now our icon slides out and slides back in.
And let me also make this a longer animation by specifying a custom animation with a duration of two seconds.
Now we can see our animation in more detail and we can also see what happens if we tap on it while the animation is still going.
It turns around and comes right back.
Again, our animation is always interactive and we can always tap on it and it will end up in the right state.
So that's our detail view.
Now let's review what we just built.
Our detail view is configured with a room to show and remember that that's a derived value passed in by the parent of the view.
And we also have our state property which controls whether this view is zoomed in or not.
And this is persisted by the framework and controls the aspect ratio.
Then we also have our video icon and that's only shown for views that have video conferencing and only when they're not zoomed.
And we're also specifying this transition to make the icon slide in and out.
But what's actually happening during that transition? Well, when this icon is removed, the view gets animated to a new position and SwiftUI waits until it finishes that animation to actually remove the view from the hierarchy.
And the when it's coming back, SwiftUI inserts it off-screen and the moves it back in with an animation.
I've wanted to be able to do AddSubview and RemoveSubview with an animation for a really long time, so I'm really excited to finally have it.
And recall that this animation is always interactive right out of the box.
This is where being data-driven instead of event-driven really shines.
All those events that Kyle talked about can happen while this is animating.
And animations beginning and ending are even more events.
It's incredibly difficult to build something like this in an event driven world.
But in SwiftUI it's just one line of code.
Now let's go back to our list of rooms and finish up this app.
Over time, we need to be able to change our list of conference rooms, so let's add some editing support.
And while we're at it, let's also make our data model a little more real.
Right now, the data in our app is completely static.
We have this array of rooms and whatever we start with is what we'll always have.
So let's update our model to have a root store object that will contain our rooms and will be able to change over time.
I'm going to drag in a prebuilt model file with our room store.
Notice that our store is a mutable object which contains the rooms that we need.
And all we need to do is tell SwiftUI when it changes.
To do that, I'm going to conform it to the bindable object protocol which requires me to have a DidChange property.
Now new this year is the Combine framework which includes a large number of components you can use to connect your data together.
Here we use the pass-through publisher, a pass-through subject from Combine which gives us a local object that we can subscribe to and send updates to, similar to a notification center.
Then we'll just update our rooms to have a DidSet so that we can notify our subject when our rooms change.
And if you're interested to learn more about Combine, there are two sessions this week to take you through all of the details.
Now let's go back to our view and update it to use our store.
We'll change from this Rooms property to a Store property.
And we'll make it an object binding to tell SwiftUI to listen to changes for this property.
And again, the Data Flow Through SwiftUI session that Kyle mentioned earlier has a lot more information about how object binding and these other pieces work.
Let's also update our preview to create our new store type.
Using our test data.
And we'll also update our list to pull the rooms from out of the store.
Great.
Now we're using our new model and whenever it updates, our view will create a fresh rendering.
This means we're ready to add our editing support.
Let's start by adding a button to our list to add new rooms.
Right now, we're using a single collection to drive the list which is great for lists that are entirely data-driven.
But when I need more, SwiftUI also lets me mix static and dynamic content in lists and other containers.
So I can replace this list using the collection with a ForEach.
A ForEach creates a view for each item in its collection.
So now I can add a static element right alongside this ForEach.
I'll just go to the library and find a button.
And then I can just drag it into my code to add it to our list.
Let's update its text to show Add Room.
And let's add a method to add that new room.
Okay, we'll tell our Store to append a new room.
And let's just use the room that we're in.
It's called Hall 2 and I think there's what, about 2,000 of you.
And finally, let's update our button to use our new Add Room method.
Okay, now let's go to Live Mode and try out our new button.
There it is, right next to all of our data.
And when I tap it, we get our new room.
Great.
So just like that, we were able to add this single static element alongside our data-driven collection.
SwiftUI lets us easily describe these powerful combinations which makes it so much easier to build complex list UI's.
No more off by one index path errors.
But I want to style this to look even better.
Let's put the Add button and all of our content into separate sections.
We can change our list style to be grouped, which gives us this nice grouped appearance.
Then we'll add a section container around our button.
And another one around our ForEach.
Great, now we have our separate sections.
Next, let's hook up deletion for our list.
We'll add a method to delete a set of rooms and we'll pass in some offsets for where to remove them.
Then we'll just tell our store to remove the rooms that those offsets.
Then we can add a modifier onto our ForEach called OnDelete.
And we can pass in our delete method to that modifier.
Now if we go back into Live Mode, we can swipe on one of our rows and delete it, just like that.
This ForEach is now configured to call into our callback whenever items get removed from it.
And then our callback calls into the Store to remove those items.
And then our view updates.
Okay.
Now we want to be able to take our list into Edit Mode in addition to just allowing swipe to delete.
So let's set a navigation bar item, and we can do that the same way we set this navigation bar title-- with another modifier.
And to create an Edit button, we just create an Edit button.
And there it is in our UI.
And while we're at it, let's also add reordering support.
Again, I'll just add a simple method to move items.
And we'll move it from a source to a destination.
And again, we'll just call into our Store's Rooms and tell it to move.
Okay.
Then just like before, we'll add another modifier, this time on Move, and tell it to call into the method that we just added.
Now let's try our app again.
We can toggle Edit Mode for our list.
And notice that all of our data rows have editing controls but the button does not.
SwiftUI automatically shows the right editing controls in the places that need it, without us having to do any extra work.
Yeah, it's cool.
And of course now we can drag to reorder and tap on items to remove them.
Thank you.
So let's quickly review what we just added.
We customized our list to show multiple sections, and by setting its list style to grouped.
And we mixed this static button together with our data-driven collection from our Rooms.
And we also saw how we can quickly add editing operations to our list with just these modifiers and a few functions to modify our data.
And remember how we made our room type identifiable earlier? Well, ForEach automatically watches for changes to its collection and synthesizes the correct insertions, deletions, and changes for us, so we no longer need to tell the list to add and remove rows, which means we no longer have to worry about getting data source inconsistency exceptions.
Yep, that's right.
So that's our list.
And we made this whole sophisticated list UI with just this really minimal view code.
Okay, now we were able to build this app up really quickly.
But you might be thinking that there's still a lot more work we need to do to get it ready for customers.
These days, support for dynamic type, dark mode, accessibility, localization -- these are all just expected for an app.
But with SwiftUI you get a lot more support for these behaviors automatically.
And we can use previews to really quickly test all of these.
So let's go to our preview and add some more views.
Again, I'll add a group to let us have multiple children.
And then I'll add another version of our view.
And this time we'll change the environment to use a size category that's a much larger size.
Let's go see how it looks.
And everything automatically works great.
Now --  Yeah.
It's great to get this for free.
Now the environment is a way that you can set contextual information about your views that flows down the view hierarchy and changes different aspects of any contained views all at once.
It's great for making changes to a large set of views and it's also great for customizing your previews to see your view in different contexts.
So let's add another version of our view and update the environment to set its color scheme to be dark.
And once again it all just works.
And finally, let's also see how our app works with other languages.
I have some English string files that I'll drag into my app.
And I'll tell Xcode to localize them.
Then I'll go to my project file and I'll import a localization that I have for Arabic.
Now let's go back to our view and add one more preview.
Now, if we first set the layout direction to be right-to-left, we can see that this automatically works without any extra work.
But if I also set the locale to be an Arabic locale, you can see that everything gets localized.
And even better, if we look back at our code, we didn't do anything extra to support these features.
To get our text localizable, we didn't have to mark up which strings should be localizable or not.
SwiftUI automatically infers that.
For text using string literals, it's localizable by default.
And for text that's created by getting passed a string, it defaults to getting used as-is.
This means that all of our app text like Rooms and Add Room gets localized.
But all of our content like these room names still gets passed right through.
But even better, you can finally use string interpolations and have them localized correctly.
I love string interpolations.
They're great.
We're really excited for you to start building apps with SwiftUI.
When you get all of these behaviors for free, you can concentrate on the unique parts of your app and build better apps for your customers even faster.
Now we built an iPhone app here, but you can use these same APIs and techniques across all of Apple's platforms.
And you'll get these kinds of automatic behaviors across all of them.
Okay, let's take one last pass through our app to review what we built and make sure everything is working right.
I'm a big fan of dark mode, so let's use that version.
Okay, we have our list of rooms and we can tap on one of them to see more information.
And in our detail view we can tap to zoom to full screen which hides our video icon with a transition, and that animation is always interactive.
And we can also edit our list to make changes.
Let's move this one down, and I don't think anyone really wants to use the dungeon conference room.
Actually, I'm also not sure why Kyle added this room that has an elephant.
Let's get rid of that one too.
And finally, let's add our conference room.
Great.
That's our app.
But there's one last thing that I want to point out and it's something that we didn't see.
We just built up this entire application and tested all these rich behaviors without ever once building and running our app.
Xcode previews let us view, edit, and debug our application way faster than was ever possible before.
So thank you very much.
I hope you enjoy using SwiftUI as much as I do.
It's a lot of fun.
So our goal with this SwiftUI is to give you the shortest path to a great app that's going to reach the widest audience.
We saw four of SwiftUI's key design principles at play today.
We saw its declarative syntax, which will evoke the actual UI you're building and take care of those imperative details like adding and removing subviews on your behalf.
We saw the compositional pieces and how you can combine together pieces of content, modifiers and containers to build exactly the UI you're looking for.
We saw all the automatic behaviors you get by saying less and letting the framework take care of more.
We talked about how SwiftUI keeps your views in a consistent state so you never end up with a view missing or in the wrong place.
And of course we played with SwiftUI's awesome interruptal animations, which is one of my favorites.
I always felt like before I had to trade between having flashy animations and the crushing complexity that could come with it.
But no longer.
The goal with SwiftUI -- wait, we didn't look at it again.
It's so cool, right? All right, the goal with SwiftUI is for us to take care of these basic features that every app needs on your behalf.
Because when you're building an app, it's not just the basic features you add.
You've got all your special, unique features that make your app yours.
And the goal is for us to bear more of this burden, the burden for all those things that you need to have to have a great app and let you spend more of your time focusing on things that make your app special.
So I hope you all enjoyed your introduction to SwiftUI.
Come find us in the labs.
We'll be there this afternoon and throughout the week.
And we called out to a couple sessions, Data Flow Through UI, and Building Custom Views.
Your next stop in learning SwiftUI should be the SwiftUI Essentials talk where we're going to go into every piece of syntax and all the pieces that you can compose together to make views what they are.
So I hope to see you there.
Have a great WWDC and I hope you enjoy SwiftUI.

