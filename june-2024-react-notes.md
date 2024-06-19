
# React Crash Course

## Pages Router vs App Router
### Pages Router
- Been around for many years
- very stable
- used in many existing NextJS propjects
- Allows you to build feature-rich fullstack apps with Reat

### Apps Router
- Introduced with NextJS 13
- Marked as stable, but still relatively new & partially buggy
- Supports modern Next & React features (-> full stack React apps)
- The future of NextJs

## React Hooks

React Hooks all start with "use". You must use React Hook functions within React components; you can't use them within bare JavaScript functions.

## Passing prop as "true"

If you set a prop that is meant to be true when you pass it to a component

	<dialog open="true" className=...>

Then you can also just pass the prop name, and true will be used as a default value

	<dialog open className=...>

## Rendering content conditionally

You can use a ternary operator:

	return (
		<>
			{modalIsVisible ? (
				<Modal onClose={hideModalHandler}>
					<NewPost
						onBodyChange={bodyChangeHandler}
						onAuthorChange{authorChangeHandler}
					/>
				</Modal>
			) : null }

			...// Other JSX Code
		</>
	);

You can also output the value *null* or *false* as part of your JSX code, which will lead to nothing being output

You can also use something like this to return content. You can use JSX as a value for anything that accepts it.

	let modalContent;

	if (modalIsVisible){
		modalContent = ( <Modal onClose={hideModalHandler}>
			<NewPost
				onBodyChange={bodyChangeHandler}
				onAuthorChange{authorChangeHandler}
			/>
		</Modal>
		);
	}

	return( 
	<>
		{modalContent}
		...// Other JSX Code
	</>
	);

Or use this:

	return(
		<>
			{modalIsVisible && (
				<Modal onClose={hideModalHandler}>
					<NewPost
						onBodyChange={bodyChangeHandler}
						onAuthorChange{authorChangeHandler}
					/>
				</Modal>
			)}

			...// Other JSX Code
		</>
	)

All 3 approaches are fine, just different methods to do the same thing.


## State Management

It's a common convention to start a prop with "on" (ex: onCreatePost) if that prop is meant to receive a function.


## Form Buttons

Add a "type" to a <button> element to stop it from submitting a form automatically

	<button type="button">Cancel</button>
	<button>Submit</button>

For the Submit button, you could also use type="submit"


## Updating State Based on Previous State

You could use a function like this to add a post to the start of the posts state object:

	function addPostHandler(postData){
		setPosts([postData, ...posts])
	}

However, this isn't the most optimal solution.

There's a rule. If you update state, and that new state is based on that previous state value, you should actually pass a function to the set method of the state. Like so:

	function addPostHandler(postData){
		setPosts( (existingPosts) => [postData, ...existingPosts] )
	}

existingPosts standing in for the current value of the state.

The reason for this is that, internally, React doesn't actually run your state updating functions instantly, but schedules those state updates. And, if you have multiple state updates after each other, you could potentially update your state based on some old state. This way makes React ensure that you get the latest correct state for this state update, even if you have multiple pending state updates.

Not just for arrays, but for any state where the new state is dependent on the old state.

## Sending a POST HTTP Request

He's got a dummy backend file app.js which is actually a REST API used for all of the backend logic. He has this coded up in Node and ExpressJS, and stores the posts in a posts.json file.

While you would actually likely use two different servers; one for running the frontend and one for running the backend, in this local dev scenario, he's running both on his local machine and running them on different ports to simulate the machines. For example, the backend interface is running on port 8080.

To get a request to the backend API route, we can use the fetch() Javascript function, which is built into JavaScript out of the box and isn't a React feature. But, unlike the name suggests, you can use this function to fetch *and* send data.

For example, you'll use something like this to save a post:

	fetch("http://localhost:8080/posts",{
		method:"POST",
		body: JSON.stringify(postData),
		headers: {
			'Content-Type':'application/json'
		}
	});

This achieves us making a new post and publishing it into the JSON file, but we might also want to fetch all of the current posts, which becomes trickier.

## Handling Side Effects with useEffect()

So, now we need to fetch all the posts we currently have. However, this becomes problematic. Fetching posts from the backend takes a little bit, and so the fetch() method doesn't execute immediately.

You might think about using an async JavaScript function and awaiting that value, but component functions need to return JSX code, and async functions return Promises. So this isn't really supported.

Another method to fetch our posts might look something like this:

	fetch("http://localhost:8080/posts").then(
		response => response.json()
	).then(
		data=> setPosts(data.posts)
	);

However, you can't do this, because changing the state with that setPosts call would reload the component since the state was changed, causing an infinite loop!

So how to do this? Thankfully, React has a hook for this since this is a common problem.

The hook is useEffect, which is used to kind of "cause side effects" in your component function. It can do something that doesn't directly affect the JSX code, but may indirectly in the future, or does anything that's not involved with directly rendering the UI.

useEffect is used to run "side effects" like so. You pass a function and an array, the latter which we will talk about later. This function will be executed by React whenever React considers this effect to require execution.

	useEffect(() => {
		async function fetchPosts(){
			const response = await fetch("http://localhost:8080/posts");
			const resData = await response.json();
			setPosts(resData.posts);
		}

		fetchPosts();
	}, [])

So he can now create that async function we discussed earlier INSIDE the useEffect effect function. Keep in mind that the useEffect function should not return a promise, but should return nothing at all. 

React will now decide when the useEffect function will execute, which will not be every time the component updates.

At this point, we will be able to load all the posts without causing an infinite loop, because the useEffect makes sure it doesn't execute always when the component reloads.

The array argument is involved in declaring exactly when the useEffect function should execute, and specifies all dependencies of the useEffect function. These dependencies are variables outside the useEffect function and, when one of these dependencies change, the useEffect function is triggered.

With an empty array, the useEffect function has no dependencies, and therefore it will be executed once when the component is first rendered and then never again.

## Handle Loading State

The application runs super fast because the frontend and backend are being run on your local machine, but it's likely that there will be some delay while fetching the data on a live web server.

For this reason, when a delay is added into the code, the "No Posts Exist" message appears right before the state is updated with the list of posts, giving a confusing UI. It would be better to add some loading text while the list of posts is being loaded.

To achieve this, he adds a state for "is fetching", which is set to "true" when the program is fetching the posts and set to "false" after the program is done;

	const [isFetching, setIsFetching] = useState(false);

	useEffect(() => {
		async function fetchPosts(){
			setIsFetching(true);
			const response = await fetch("http://localhost:8080/posts");
			const resData = await response.json();
			setPosts(resData.posts);
			setIsFetching(false);
		}

		fetchPosts();
	}, [])

Then he just uses that state to stop the "No Posts" and "Posts" text from showing. And sets up a brand new part of the component that shows the "Loading posts..." message:

	{isFetching && <div style={{textAlign:'center', color:'white'}}><p>Loading Posts...</p></div> }

This is how he deals with a loading state. He also suggests that you might want to handle an error state in the fetchPosts() functions and print out an error if the response is not okay. But he leaves that as a user exercise. You could use something like so:

	useEffect(() => {
		async function fetchPosts(){
			setIsFetching(true);
			const response = await fetch("http://localhost:8080/posts");
			const resData = await response.json();

			if(!response.ok) {
				// do something
			}

			setPosts(resData.posts);
			setIsFetching(false);
		}

		fetchPosts();
	}, [])


## Understanding and Adding Routing

Almost all React Apps, minus simple demos, might have multiple paths that load different pages for those different paths. React creates single-page applications, but still allows you to have different components on different paths. So for /, you might want to load a homepage, /products/ to load a Products page, etc...

React Router allows you to do this even though it's a SPA. Install via:

	npm install react-router-dom

## Adding Routes

He is going to add a route for both a Post Details page and a New Post page that shows the modal.

Add this to your top level main.jsx component like so. Replace the \<App\> component within the "React.StrictMode", with this RouterProvider component.

	
	import { RouterProvider } from 'react-router-dom';

	import App from "./App"
	import "./index.css"


	ReactDOM.createRoot(document.getElementByID("root")).render(
		<React.StrictMode>
			<RouterProvider />
		</React.StrictMode>
	)

However, we still need to write out the individual routes. For example, this declares a route for the homepage and one for a new post:

	import React from 'react'
	import ReactDOM from 'react-dom/client'
	import { RouterProvider, createBrowserRouter } from 'react-router-dom';

	import App from "./App"
	import NewPost from "./components/NewPost"
	import "./index.css"

	const router = createBrowserRouter([
		{
			path:"/",
			element: <App />
		},
		{
			path:"/create-post",
			element: <NewPost />
		}
	]);

	ReactDOM.createRoot(document.getElementByID("root")).render(
		<React.StrictMode>
			<RouterProvider router={router} />
		</React.StrictMode>
	)

However, the one for the New Post doesn't really work that well, as it pulls that component out of the overall page, so it doesn't add posts correctly and it doesn't look as it should.

To fix this, we'll dive into the React concept of Layout Routes.

## Working with Layout Routes

When building more complex React apps with routing, it's quite common that some routes should have common layout elements, such as a top header bar.

To achive this, you can add so-called "Layout Routes". This is the syntax for our New Post Route:	

	import RootLayout from "./routes/RootLayout";
	...
	...
	const router = createBrowserRouter([
		{
			path:"/",
			element: <RootLayout />,
			children:[
				{
					path:"/",
					element: <App />
				},
				{
					path:"/create-post",
					element: <NewPost />
				}
			]
		},
<!-- 		{
			path:"/",
			element: <App />
		},
		{
			path:"/create-post",
			element: <NewPost />
		} -->
	]);

A few things. Firstly, he created a new RootLayout that basically has the header bar within the a new folder under /src/routes/. He explains that components that are used in other Routes should be kept in the /components folder, but actual Route or Layout Routes should be kept within the /routes folder

The RootLayout.jsx file in /src/routes/ has the following within it:

	import { Outlet } from 'react-router-dom';
	import MainHeader from "../components/MainHeader";

	function RootLayout(){
		return (
			<>
				<MainHeader />
				<Outlet />
			</>;
		)
	}

	export default RootLayout

The Outlet component is a special component provided by React that should be rendered in the place where the actual nested route content should be "injected". This allows the previous RootLayout component to be used for both paths.


## Refactoring Route Components and More Nesting

Moves main App.jsx into /src/routes/ and renames it to Posts.jsx. removes MainHeader and renames the component function.

Moves NewPost.jsx into the /src/routes/ folder and sets it to be wrapped by a <Modal> component

So the PostLists component does get shown in the background of the New Posts component, he puts it in as a layout route:

	const router = createBrowserRouter([
		{
			path:"/",
			element: <RootLayout />,
			children:[
				{
					path:"/",
					element: <Posts />,
					children: [
						{
							path:"/create-post",
							element: <NewPost />
						}
					]
				},
			],
		},
	]);

Also changes Posts.jsx to have an <Outlet/> component above the <PostsList/>

However, you can't close the modal and can't use the "New Post" button yet.

## Linking & Navigating

To make sure that the NewPost brings up that NewPost route, we need to replace that button with an <a> element that links directly to the /create-post/ route. So you should do the following. Change the existing code:

	<button className={classes.button} onClick={onCreatePost}>
		<MdPostAdd size={18} />
		New Post
	</button>

To this new code, using the Link attribute:

	import { Link } from 'react-router-dom';
	...
	...
	<Link to="/create-post" className={classes.button}>
		<MdPostAdd size={18} />
		New Post
	</Link>

The Link element uses the "to" property instead of "href", but you should still put in the URL of your route.

You can also add a closeHandler to your Modal component,which uses the useNavigate hook.

	import { useNavigate } from "react-router-dom";
	...
	...
	const navigate = useNavigate();

	function closeHandler(){
		navigate("/");
	}

This will navigate back to the homepage, but you can do multiple things here. You could use .. to navigate up one level. This is similar to .. in how it's used in the terminal:

	...
	navigate("..");
	...

This navigates the Modal up to the parent route.

We can also set the Cancel button to send the user up to the parent route:

	<Link to="..">
		Cancel
	</Link>

Now, everything is working and you have easily shareable routes!

## Data Fetching via loader()s
react-router-dom (6.4 or higher) actually also has methods and infrastructure for fetching and submitting data, which we will look into next.

You can use the useEffect hook for loading and setting data like we already are, but you can also more conveneiently add a loader property to your route definition that will load data:

	import Posts, { loader as postsLoader} from "./routes/Posts";
	...
	...

	const router = createBrowserRouter([
		{
			path:"/",
			element: <RootLayout />,
			children:[
				{
					path:"/",
					element: <Posts />,
					loader: postsLoader,
					...
				},
			],
		},
	]);

And then you can go to your route file and define the following:

	...
	export default Posts
	...
	...
	export async function loader(){
		const response = await fetch("http://localhost:8080/posts");
		const resData = await response.json();
		return resData.posts;
	}

React doesn't mind whether the loader property of the route is an async function or not and if the function returns a Promise, React will wait on the resolution of the Promise to show the element under "element"

Then you can make these changes to your component:

	import { useLoaderData } from 'react-router-dom';
	...
	...
	...
	const posts = useLoaderData();


Now, sadly, you'll see that the route isn't rendered until the loading resolves. If you want the application to behave differently, React gives you options to show pages earlier, but is beyond the scope of this course.

This is a great solution for a fast backend, but not so good for a slow one, because the page will be empty for that few seconds that the backend is loading the content


## Submitting Data with action()s

So now we can load data, but what about submitting data?

You can also add an action() function to routes with the "action" property. This function under the "action" property will be triggered when a FORM IS SUBMITTED within that route:

	...
	...
	import NewPost {action as newPostAction} from "./routes/NewPost";
	...
	...

	const router = createBrowserRouter([
		{
			path:"/",
			element: <RootLayout />,
			children:[
				{
					path:"/",
					element: <Posts />,
					loader: postsLoader,
					children: [
						{
							path:"/create-post",
							element: <NewPost />
							action: newPostAction
						}
					]
				},
			],
		},
	]);

And in the NewPosts.jsx route file:

	...
	...
	export default NewPost;
	...
	...

	export async function action({request}){
		const formData = request.formData();
		// formData.get('body');	
		const postData = Object.fromEntries(formData);// creates basic key-value object

		// const res = await fetch("http://localhost:8080/posts",{
		await fetch("http://localhost:8080/posts",{
			method:"POST",
			body: JSON.stringify(postData),
			headers: {
				'Content-Type':'application/json'
			}
		});

		return redirect("/"); // After submitting data, move to the homepage route
	}


And you can remove all the ev.preventDefault() call and stuff like that.

Then you just need to add "name" attributes to your form that matches what is stored in your postData. Also, replace the default <form> element within your code with the <Form> component from react-router-dom within NewPost.jsx:

	import { Link, Form } from 'react-router-dom';
	...
	...

	<Modal>
		<Form method="post" className={classes.form}>
			...
		</Form>
	</Modal>

This is a special Form element that means that react-router-dom will 
- Handle the Form Submission
- Prevent the browser default of sending a request
- but will still send an object with that user data and use the action() function

## Dynamic Routes

Final Task is to create functionality that, when you click on a post, that it opens that post within a Modal for your viewing.

Add a Dynamic Route for this, so you can look up the details of the post based on Post ID:

	...
	...
	import PostDetails, {loader as postDetailsLoader } from "./routes/PostDetails";

	const router = createBrowserRouter([
		{
			path:"/",
			element: <RootLayout />,
			children:[
				{
					path:"/",
					element: <Posts />,
					loader: postsLoader,
					children: [
						{
							path:"/create-post",
							element: <NewPost />
							action: newPostAction
						},
						{
							path:"/:id", //dynamic path parameter; can be any name
							element: <PostDetails />,
							loader: postDetailsLoader
						}
					]
				},
			],
		},
	]);

For the element that the route points to, he has the "PostDetails.jsx" and "PostDetails.module.css" files within the /routes/. It uses useLoaderData() to get the post details, so we'll use a loader for this route.

	...
	...
	export async function loader({params}){
		const response = await fetch("http://localhost:8080/posts/" + params.id);
		const resData = await response.json();
		return resData.post;
	}

Use the same variable off of params that you used in the Route.

params also exists for action() functions, by the way.


# NextJS Essentials (App Router)
