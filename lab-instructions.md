::page{title="Final Project: Paradise Nursery Shopping Application"}

<img src="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-WD0231EN-SkillsNetwork/IDSN-logo.png" width="200" alt="cognitiveclass.ai logo"  />

**Estimated time needed:** 1 hour

## Introduction

In this final project, you will create a shopping cart application for an online plant shop which offers a variety of house plants.

The *Paradise Nursery* shopping cart features will include:
- A Landing page with a button linking to the product listing page
- A navigation bar with links to the landing, product listing, and shopping cart pages
- A card for each plant that showcases the different plants along with their images, name, description, cost and an **Add to cart** button.
- A minimum of two sections describing the plants in that section. For example, \"Aromatic Plants\" and \"Medicinal Plants\".
- A cart page which displays the products in the cart.
- The cart should have a card for each type of plant in the cart. Each card should have the thumbnail, the unit cost, the cost for all of the plants of that type and buttons to increase and decrease the quantity along with **Delete** button.
- A **Continue Shopping** and **Checkout** buttons

You will apply the knowledge and skills gained from the practice project to implement dynamic functionalities in the final project. Hence it is recommended to complete the practice project before attempting the final project. For example, features like displaying the cart quantity in the navbar icon and updating the total cost when the user changes the item quantity will be part of the final project.

## Note:
1. Please ensure that all you files are updated and pushed to the public github repository and your deployed URL is live and publically accessible.

2. As mentioned in the *\"Final Project Overview\"*, you can submit your project deliverables through either Option 1: AI-Graded Submission and Evaluation or Option 2: Peer-Graded Submission and Evaluation.

4.  **Option 1: AI-Graded Submission and Evaluation**  
  Submit the **public GitHub repository URLs** for the following project files: README.md, AboutUs.jsx, App.css, App.jsx, CartSlice.jsx, ProductList.jsx, and CartItem.jsx. Your project code must be stored in a **public GitHub repository named `e-plantShopping`**.

5.  **Option 2: Peer-Graded Submission and Evaluation**  
  Submit the **deployed application URL** and the **public GitHub repository URL** for peer evaluation.When you deploy, make a note of the **live application URL**
Please ensure-
 - All project files must be **committed and pushed** before submission.  
- Your application must be **deployed** and the **live URL** should be available.  
- You may host your app using **GitHub Pages** or any other hosting platform of your choice.  

## Learning objectives
After completing this lab, you will be able to:

- React Components: Create functional React components using component composition and nesting.
- State Management with Hooks: Implement React Hooks, specifically the useState and useEffect hooks. You will manage component-level state using hooks to control the visibility of elements.
- Redux Integration: Integrate Redux within an application using Redux concepts like actions, reducers, and the store.
- Rendering Dynamic Data: Dynamically render data fetched from an array of objects into the UI. You will map over arrays to generate lists of components.
- Handling Events and Conditional Rendering: Handle user events such as button selection and trigger corresponding actions.

## Prerequisites

- Basic knowledge GitHub and your own GitHub account
- Understanding of React function components, props, hooks and React Redux Toolkit
- Web browser with a console (such as Chrome DevTools or Firefox Console)
- It is mandatory to complete the Practice Project

::page{title="Important notice about this lab environment"}

Skills Network Cloud IDE (based on Theia and Docker) is an open-source IDE (Integrated Development Environment) that provides an environment for hands-on labs in course and project-related labs.

Please be aware that sessions for this lab environment are not persistent. Every time you connect to this lab, a new environment is created for you. You will lose data if you exit the environment without saving to GitHub or another external source. Plan to complete these labs in a single session to avoid losing your data.

::page{title="Setting up your environment in GitHub"}

1. Fork the repository

You need to fork the GitHub repository for your React application. The GitHub repository with the skeleton code for this project is here.Please use the same repository name when creating your fork:
- https://github.com/ibm-developer-skills-network/e-plantShopping.git

- After following the link above, click on the fork button.

![fork the repository](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/zZMZUZ0Q4zl7koVz2OhbPQ/e-plantshoprepository.png "fork the repository")

2. This repository contains the basic layout of the React application for this project.

3. You will use this forked repository to push your latest code to keep a record of the work you do. Periodically save all your files. Your files must be saved to perform git commands.

4. Perform `git add`, `git commit`, and `git push` commands to update changes from your application folder to your GitHub repository for proper code management.

5. As part of the peer review project (if you choose this option) , you will need to deploy your app so your peers can review the UI. You can review [these instructions](https://cf-courses-data.static.labs.skills.network/IBMSkillsNetwork-CD0210EN-Coursera/labs/v2/m1/Setting_up_the_environment.md.html) for assistance with GitHub and for deployment instructions of react application.


If you\'ve logged out and want to resume work on the project, clone the forked repository where you previously pushed the code. After cloning, you can use `git push origin` without the need to execute `git remote add...` to push your changes directly.

::page{title="Create your React project"}

1. If you do not have an open terminal, select the \"Terminal\" tab at the top-right of the window, and then select \"New Terminal\". The screenshot below shows you where to locate these options on your screen.

	![SN screenshot](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CD0210EN-Coursera/images/terminal.png)

2. Now clone the forked repository using given command by replacing `<forked-repo-link>` with your own repository link.

	```javascript
	git clone <forked-repo-link>
	```
*Note: You should keep the original repository name e-plantShopping*

3. Make sure your application name matches your project.

<!--4. You can either find your own images for the project or use these suggested images from *[Pixabay](https://pixabay.com "Pixabay")* and *[Unsplash](https://unsplash.com "Unsplash")*, sites that supplies royalty-free images.

[License information for Pixabay images](https://pixabay.com/service/license-summary/ "License information for Pixabay images")

[License information for Unsplash images](https://unsplash.com/license "License information for Unsplash images")

Use the `wget` commands below to retrieve the images from Pixabay and Unsplash. Make sure you `cd` to the correct folder so the files download to the appropriate directory.

- Snake plant:
	```bash
	wget https://cdn.pixabay.com/photo/2021/01/22/06/04/snake-plant-5939187_1280.jpg
	```
- Spider plant:
	```bash
	curl https://pixabay.com/images/download/chlorophytum-3530413_640.jpg -o chlorophytum-3530413_640.jpg
	```
- Peace lily:

	```bash
	curl https://pixabay.com/images/download/peace-lilies-4269365_640.jpg -o peace-lilies-4269365_640.jpg
	```

- Boston fern:
	```bash
	curl https://pixabay.com/images/download/boston-fern-5114414_640.jpg -o boston-fern-5114414_640.jpg
	```
- Rubber plant:
	```bash
	curl https://pixabay.com/images/download/flower-4850729_640.jpg -o flower-4850729_640.jpg
	```
- Aloe vera:
	```bash
	curl https://pixabay.com/images/download/leaf-3283175_640.jpg -o leaf-3283175_640.jpg
	```
- Lavendar:
	```bash
	wget https://images.unsplash.com/photo-1589296986498-28cd9406425d
	```
- Jasmine:
	```bash
	wget https://images.unsplash.com/photo-1592729645009-b96d1e63d14b
	```
- Rosemary:
	```bash
	wget https://cdn.pixabay.com/photo/2019/10/11/07/12/rosemary-4541241_1280.jpg
	```
- Mint:
	```bash
	wget https://cdn.pixabay.com/photo/2016/01/07/18/16/mint-1126282_1280.jpg
	```
- Lemon balm:
	```bash
	wget https://cdn.pixabay.com/photo/2019/09/16/07/41/balm-4480134_1280.jpg
	```
- Marigold:
	```bash
	wget https://cdn.pixabay.com/photo/2022/02/22/05/45/marigold-7028063_1280.jpg
	```
- Basil:
	```bash
	wget https://cdn.pixabay.com/photo/2015/09/09/17/38/basil-932079_1280.jpg
	```
- Catnip:
	```bash
	wget https://cdn.pixabay.com/photo/2015/07/02/21/55/cat-829681_1280.jpg
	```
- Echinacea:
	```bash
	wget https://cdn.pixabay.com/photo/2014/12/05/03/53/echinacea-557477_1280.jpg
	```
- Peppermint
	```bash
	wget https://cdn.pixabay.com/photo/2017/07/12/12/23peppermint-2496773_1280.jpg
	```
- Chamomile:
	```bash
	wget https://cdn.pixabay.com/photo/2016/08/19/19/48/flowers-1606041_1280.jpg
	```
- Calendula:
	```bash
	wget https://cdn.pixabay.com/photo/2019/07/15/18/28/flowers-4340127_1280.jpg
	```
- ZZ plant:
	```bash
	wget https://images.unsplash.com/photo-1632207691143-643e2a9a9361
	```
- Pothos:
	```bash
	wget https://cdn.pixabay.com/photo/2018/11/15/10/32/plants-3816945_1280.jpg
	```
- Cast iron plant:
	```bash
	wget https://cdn.pixabay.com/photo/2017/02/16/18/04/cast-iron-plant-2072008_1280.jpg
	```

- Succulents:
	```bash
	wget https://cdn.pixabay.com/photo/2016/11/21/16/05/cacti-1846147_1280.jpg
	```

- Aglaonema:
	```bash
	wget https://cdn.pixabay.com/photo/2014/10/10/04/27/aglaonema-482915_1280.jpg
	```
-->
4. After cloning the repository you will see the folder structure like given screenshot.

	![FP ss.png](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/TAc03c4e3Ri6PuTggre2Aw/FP%20ss.png)

5. Write the command to enter the application folder in the terminal. The command will set your terminal path to run the React application in the `<forked-folder-name>` folder.
	```bash
	cd e-plantShopping
	```
6. To make sure that the code you have cloned is working correctly, you need to follow the given steps:
	- Write the following command in the terminal and select Enter to install all the necessary packages to execute the application.

		```bash
		npm install
		```
	- Then execute the following command to run the application, providing you with port number 4173.

		```bash
		npm run preview
		```

7. To view your React application, click the Skills Network icon on the left panel (refer to number 1). This action will open the **Skills Network Toolbox**. Next, click **Launch Application** (refer to number 2). Enter port number **4173** in **Application Port** (refer to number 3) and click ![arrow pointing outside of a box](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CD0210EN-Coursera/images/6.png).

	![Launch Your Application](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/7Zp_Csloj8ZcONEZiA4jbw/launch-app.jpg)

8. The output will be according to given screenshot with background picture.

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/rdrEbBnT64JcAfhcKQHQUg/landing-plant.png)



9. Now click on `Get Started` button and then you will see the given layout according to screenshot which includes navbar with green background color.
	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/4YbW3vHz8RyXrcf07wbyZg/navbar-plant.png)

<!--10. Create a basic directory structure by creating the following components and files within the `src` folder.
	- `CartItem.jsx` component
	- `CreatSlice.jsx` component-->

10. The navbar contains three links:
	- `Paradise Nursey`- This will take you back to the landing page of the application.
	- `Plants`- This will navigate you to the page where information related to page will be visible.
	- `Cart icon`- This will navigate you to the cart items section.

11. When you will click on `cart icon` output will be visible as per given screenshot.

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/1RpDJP4KErhPyBQNBthkvw/cartItem.png)

Complete the required tasks explained on the pages that follow. You will assessed based on these tasks.

<!--::page{title="GitHub Pages"}

enter info about needing the link to their github page here for the peer review-->

::page{title="Updating the Readme.md file"}

Open your README.md file in your GitHub repository.

Includes the repository name e-plantShopping in the contents of the file.You can also mention the project name and provides a brief overview of your application

Note : Make sure the file includes the repository name e-plantShopping in the contents.

Make sure that you save these changes by pushing your code to your GitHub repository.

`Note : This step can be skipped if you choose to proceed with the Peer Graded Assignment.`

::page{title="Task 1: ProductList component Layout"}


The product page will allow your users to shop for the different plants you sell. Each plant will display on its own \"card\" with its related data stored in the plant object. You will store the plant objects in an array. Follow these steps for the array and plant objects.

1. Display the Plant Array
- Navigate to the `ProductList.jsx` component and you will see an array named `plantsArray` with the plants details.
- Each plant object contains the categories, properties name, image URL, description, and cost.

2. Display Plant Details within `div` tag with class name **product-grid**.
- Utilize array methods to map over the plant array.
> Hint: use the `map()` method to iterate array.
 
- Render each plant\'s details on the page, including name, image, description, and cost.

3. Display an **Add to Cart** button for each plant.
 
	
<details>
	<summary>Display plants and add to cart button solution</summary>

```javascript
{plantsArray.map((category, index) => ( // Loop through each category in plantsArray
  <div key={index}> {/* Unique key for each category div */}
    <h1>
      <div>{category.category}</div> {/* Display the category name */}
    </h1>
    <div className="product-list"> {/* Container for the list of plant cards */}
      {category.plants.map((plant, plantIndex) => ( // Loop through each plant in the current category
        <div className="product-card" key={plantIndex}> {/* Unique key for each plant card */}
          <img 
            className="product-image" 
            src={plant.image} // Display the plant image
            alt={plant.name} // Alt text for accessibility
          />
          <div className="product-title">{plant.name}</div> {/* Display plant name */}
          {/* Display other plant details like description and cost */}
          <div className="product-description">{plant.description}</div> {/* Display plant description */}
          <div className="product-cost">${plant.cost}</div> {/* Display plant cost */}
          <button
            className="product-button"
            onClick={() => handleAddToCart(plant)} // Handle adding plant to cart
          >
            Add to Cart
          </button>
        </div>
      ))}
    </div>
  </div>
))}

```

</details>

- Include above code within class name **product-grid**.

4. Create one variable named `addedToCart` for state management using the **useState** hook to track which products are added to the cart.
 
<details>
<summary>Sample solution for useState hook</summary>

```js
const [addedToCart, setAddedToCart] = useState({});
```
</details>
 
5. Add to Cart Functionality
- Create the `handleAddToCart` function to implement the functionality for adding a plant to the cart when the user selects the **Add to Cart** button. This function should take one parameter that contains the information of the selected plant. This information should then be dispatched to the addItem inside the function component `CartSlice`.
 
- Additionally, reflect the product has been added to the cart. Update the `setAddedToCart` state to by setting the product name as a key and its value to true.

<details>
<summary>Sample solution for add to cart</summary>

```js
const handleAddToCart = (product) => {
  dispatch(addItem(product)); // Dispatch the action to add the product to the cart (Redux action)

  setAddedToCart((prevState) => ({ // Update the local state to reflect that the product has been added
    ...prevState, // Spread the previous state to retain existing entries
    [product.name]: true, // Set the current product's name as a key with value 'true' to mark it as added
  }));
};
```
	
</details>
 
>Note: Make sure that you `import` the `addItem` reducer from `CartSlice.jsx`
 
6. The `handleAddToCart()` function <!-- not sure what you mean by "this function"? Which function?--> will carry the details of that plant which user want to add in the cart. And the plant details to the cart at a global level using `CartSlice.jsx`.
 
7. Make sure that you save these changes by pushing your code to your GitHub repository.

::page{title="Task 2: State management using Redux"}

1. You have the basic layout in the `CartSlice.jsx` file.
	
2. Define Reducer Functions
- Now implement the reducer property of the slice for adding, removing, and updating the number of items in the cart.
- These reducer functions will be called when user wants to add or remove the quantity of plants within the `cartItems` component.
 
- The `addItem()` reducer adds a new plant item to the `items` array which you  initialized in the previous step. 
- The `addItem()` function should get called when the user selects an **Add to cart** on the plant listing page. Subsequently, the `handleAddToCart()` gets called which has the plant type as a parameter.
- The `handleAddToCart()` function will then dispatch the plant details to the `addItem()` reducer function in `CartSlice.jsx`.

<details>
<summary>addItem() reducer sample solution</summary>

```js
addItem: (state, action) => {
  const { name, image, cost } = action.payload; // Destructure product details from the action payload
  // Check if the item already exists in the cart by comparing names
  const existingItem = state.items.find(item => item.name === name);
  if (existingItem) {
    // If item already exists in the cart, increase its quantity
    existingItem.quantity++;
  } else {
    // If item does not exist, add it to the cart with quantity 1
    state.items.push({ name, image, cost, quantity: 1 });
  }
},
```
</details>

- Now you need to complete code for the `removeItem()` and `updateQuantity()` reducers.

- `removeItem()`: This reducer removes an item from the cart based on its name and gets called when the user wants to remove products from the cart.

<details>
<summary>removeItem() reducer sample solution</summary>

```js
state.items = state.items.filter(item => item.name !== action.payload);
```
</details>
	
- `updateQuantity()`: To create this function, start by extracting the item\'s name and amount from the `action.payload`. Then, look for the item in the `state.items` array that matches the extracted name. If the item is found, update its quantity to the new amount provided in the payload. This ensures the item's quantity is correctly updated based on the action.

<details>
<summary>updateQuantity() reducer sample solution</summary>

```javascript
const { name, quantity } = action.payload; // Destructure the product name and new quantity from the action payload
// Find the item in the cart that matches the given name
const itemToUpdate = state.items.find(item => item.name === name);
if (itemToUpdate) {
  itemToUpdate.quantity = quantity; // If the item is found, update its quantity to the new value
}
```
</details>

3. Handle Actions
- Export the action creators, `addItem()` to use in `ProductList.jsx`, `removeItem()`, and `updateQuantity()`, to use in the `CartItem.jsx`.
- Also export the reducer as the default to use in `store.js`.

4. Make sure you save these changes by pushing your code to your GitHub repository.

::page{title="Task 3: CartItems component"}

Next, you will complete the development of the `CartItem.jsx`component which displays the items held in the shopping cart. This component has a number of functionalities that you find in a typical shopping cart:
- Calculate the total for all items in the cart.
- Calculate the subtotal for each plant type in the cart.
- Continue shopping
- Increment and decrement the number of each plant type in the cart
- Remove (delete) a plant type from the cart altogether.

You will dispatch the increment, decrement, and update quantity details from a Redux file.

When you are done, the cart page should look similar to the following:
	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/p9Yu4z-YQsn0X0hbecMv9A/8.png)

1. Cost of all items in cart
- In the `calculateTotalAmount()` you need a function to calculate the cost of all of the items in the cart. There are a number of ways you can calculate this.

<details>
<summary>Sample algorithm description for calculating the total cost</summary>
<ul>
  <li>Initialize a variable <code>total</code> to hold the cumulative sum.</li>
  <li>Iterate over the <code>cart</code> array using <code>cart.forEach()</code>.</li>
  <li>For each item, extract its <code>quantity</code> and <code>cost</code>.</li>
  <li>Convert the <code>cost</code> string (e.g., <code>"$10.00"</code>) to a number using <code>parseFloat(item.cost.substring(1))</code>, then multiply it by the <code>quantity</code>.</li>
  <li>Add the resulting value to <code>total</code>.</li>
  <li>After processing all items, return the final <code>total</code> sum.</li>
</ul>

</details>


2. Continue shopping
- Users should be able to return to the plant listing page to continue shopping while on the shopping cart page. So, in the `handleContinueShopping()` function, call the `onContinueShopping(e)` function passed from the parent component.

3. Checkout
- In this project, you are not required to provide the `handleCheckoutShopping()` function, but you may wish to for further exploration and practice. For now, just add in the following code to alert the user this function will get added at a later date.
```js
const handleCheckoutShopping = (e) => {
  alert('Functionality to be added for future reference');
};
```

4. Increment and decrement
- For the `handleIncrement()` and `handleDecrement()` functions, you need to dispatch the `updateQuantity()` reducer in the `CartSlice.jsx` file. In the function argument, either add one to the `item.quantity` value or subtract one, respectively.

- Also, for the `handleDecrement()` you will need an if-else to handle the case.
-- If the item\'s quantity is greater than 1, dispatch `updateQuantity` to decrease the quantity by 1.
-- Else if the quantity would drop to 0, dispatch the `removeItem` action to remove the plant type from the cart.

<details>
    <summary>Click here to see hints</summary>
    <ul>
        <li>Dispatch the <code>updateQuantity</code> action (from your Redux slice) to increase or decrease the item's quantity by 1.</li>
		 <li>Use the <code>name</code> parameter of the item to identify which item's quantity needs to be updated.</li>
        <li>Example code:
            <pre><code>dispatch(updateQuantity({ name: item.name, quantity: item.quantity + 1 }));</code></pre>
        </li>
    </ul>
</details>


5. Remove plant from the cart
- For the `handleRemove()` function you need to dispatch the `removeItem` action to delete the item from the cart.

6. Item subtotal
- Calculate the total cost for an item by multiplying its quantity with its unit price in the `calculateTotalCost()` function.
- Extract the numeric value from the item\'s cost string using `parseFloat(item.cost.substring(1))` before performing the multiplication.

>Note: Ensure that these event handlers update the UI in real time. When the user changes the number of a plant type, the following should update accordingly:
•	The individual plant quantity.
•	The item\'s subtotal.
•	The overall total cost.
•	The the total number of items in the cart icon.
•	After a user clicks the \"Add to Cart\" button for a plant item, the button should become disabled and grayed out, and its label should update to \"Added to Cart\" to indicate that the item has already been added.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/8wJF2h4C8D2Q3Lh3pV0E6w/7.png)


	
7. Make sure that you save these changes by pushing your code to your GitHub repository.

::page{title="Task 4: Integrate Redux functionality in your components"}

1. ProductList Component

- Initialize the cart state within the Redux store to keep track of cart items.

<details>
    <summary>Click here to see hints</summary>
 
	dispatch(addItem(product));
</details>

- Use the `addItem` action to add selected products to the cart.
- Access the Redux store to retrieve and display the total quantity of items currently in the cart.

<details>
    <summary>Click here to see hints</summary>
	
	const calculateTotalQuantity = () => {
	 return CartItems ? CartItems.reduce((total, item) => total + item.quantity, 0) : 0;
 	 };
</details>
	
2. CartItem Component

- Use the `updateQuantity` action to change how many items are in the cart.
- Use the `addItem` action to add a new product to the cart.
- Use the `removeItem` action to delete an item completely from the cart.

<details>
    <summary>Click here to see hints</summary>
	
	dispatch(removeItem(item.name));
</details>

*Note: Make sure that you save these changes by pushing your code to your GitHub repository*

::page{title="Task 5: Import details to store.js"}

1. Importing Necessary Functions and Files:

	- The `configureStore()` function from the `@reduxjs/toolkit` package is imported to set up the Redux store.
	- The `cartReducer` from the `CartSlice.jsx` file which is imported, manages the state slice related to the shopping cart.

```js
import { configureStore } from '@reduxjs/toolkit';
import cartReducer from './CartSlice';
```

2. Configuring the Store:

	- The `configureStore()` function is used to setup the Redux store.
	- Inside the configuration object passed to `configureStore()`, the `reducer` key specifies the reducer functions. In this case, the `cartReducer` is assigned to manage the `cart` slice of the state.
```js
// Create a Redux store using configureStore from Redux Toolkit
const store = configureStore({
    // Define the root reducer object
    reducer: {
        // 'cart' is the name of the slice in the store, and it's managed by cartReducer
        cart: cartReducer,
    },
});

export default store; // Export the store for use in the app (e.g., in <Provider store={store}>)

```


3. Exporting the Store:

	- The configured Redux store is exported using `export default store;`, so it can be used throughout the application to manage state.

```js
export default store;
```


*Note: 
	- This store.js code is pre-configured in the repository and ready for use.
	- Make sure that you save these changes by pushing your code to your GitHub repository*

::page{title="Task 6:  Set up the global store"}

1. Navigate to the `main.jsx` file in the `src` folder.

2. The `Provider` component from the `react-redux` library is already imported. This component enables all components in the application to access the Redux store.
```js
import { Provider } from 'react-redux';
```

3. The Redux store is imported from the `store.js` file. This store holds the application\'s state, using the reducer defined in the `CartSlice.jsx` file.
```js
import store from './store.js';
```

4. The `App` component is wrapped with the `Provider` component, with the Redux store passed as a prop. This allows all components in the app to access and interact with the global state managed by Redux.

```js
<Provider store={store}>
  <App />
</Provider>
```

5.  Deploying Your Application with GitHub Pages

<details>
    <summary>Deploy using GitHub Pages</summary>
	
1. To deploy your react application in GitHub you need to install `gh-pages`. This allows you to use it as a tool for deploying your project to GitHub Pages. Perform given command in the terminal

	```javascript
	npm install gh-pages --save-dev
	```

2. Add given lines before `"build": "vite build"` in `package.json` file.

	```javascript
	"predeploy": "npm run build",
	"deploy": "gh-pages -d dist",
	```
![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/s9dWUlx8DN5Mit92y41b5w/package-gitpages.png)

3. Then in the vite.config.js file add this line before plugins: `[react()]`

	```javascript
	base: "/YOUR_REPOSITORY_NAME",
	```

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/sSsrlRFR5PAr08o4fUmu2Q/gitvit.png)

	*Note: Instead of <YOUR_REPOSITORY_NAME> write your own repository name such as assume if your github repository name is learning_react the it should look like  `base: "/learning_react"`*

4. Now perform deploy command in the terminal to executes the \"deploy\" script defined in the package.json file, deploying the project to GitHub Pages using the gh-pages tool.

	```javascript
	npm run deploy
	```
	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/LT5P_006mug4cqF4f_2rTA/A%20screen%20shot%20of%20a%20computer--Description%20automatically%20generated%20-1-.png)

*Note: Whenever you make any change to your code you need to save all your files and perform git commands for them.*

5. Perform `git add` and `git commit` commands to update changes in your code. Then perform `git push` command to update your GitHub repository for proper code management.

6. Go to your GitHub repository. Then, navigate to your site\'s repository that you created.

7. Under your repository name, click **Settings**.

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/N_AQG5Nn7EN40JiqcbqMyA/git-setting.png)
	
8. Navigate to the left hand side navigation bar. In the **Code and Automation** section of the sidebar, click **Pages**.

	![Settings tab with Pages circled](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-JS0101EN-SkillsNetwork/images/2_gitPages.png)

9. You will see the page shown below. Click the drop down menu where you see **None**, then click **gh-pages**, and then click the **Save** button.

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/k2GDUA3GvUXYhPBp_iVw9A/deploy-gitpoages.png)

10. Refresh your page again, and you will see the link, just as below. Instead of **shoppingreact**, you will see your github repository name.

	![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/D2d2dreQY_xxldfcDCaWxA/live-gitdeploy.png)

>**Note:** If you are not able to see the link, please wait for (1-2) minutes and refresh the page again.
  

11. Click above generated link to see your live website.

	![gh react.png](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/1WUUefvu1MvT7_CqSj3f4g/gh%20react.png)


</details>
	
Note:
- This code is pre-configured in the repository and ready for use.
- Make sure that you save these changes by pushing your code to your GitHub repository
- **After deploying on GitHub Pages, it may take some time for all contents and images to appear properly. Please wait a few extra minutes for the application to load completely.**

::page{title="Project Completion"}

### Congratulations!

You completed this project! Great work.

- If you have not already done so, deploy your application. You can deploy it using GitHub Pages or your own hosting site.
- Ensure you have pushed all the updated files to your github repository
	
### Summary

- You created function React components, composed, and nested them. 

- You implemented React Hooks, specifically the `useState` and `useEffect` hooks to manage component-level states.

-  You integrated Redux within your React application and applied Redux concepts like actions, reducers, and the store.

- You dynamically rendered data fetched from an array of objects onto the UI. You mapped over arrays to generate lists of components.

- You handled user events such as button selection and triggered corresponding actions to add and remove items in the cart.

::page{title="Checklist for Submission"}


Follow the checklist below to verify that your project meets all requirements before submission.

Submit your work through either **Option 1: AI-Graded Submission and Evaluation** or **Option 2: Peer-Graded Submission and Evaluation**, depending on the submission path you choose for project evaluation.

# Checklist for **Option 1: AI-Graded Submission and Evaluation**

After completing the final project, you should:

1. **Submit the GitHub URL of the `README.md` file** containing the project name details.
   - Ensure the content includes the repository name **`e-plantShopping`**.

2. **Submit the GitHub URL of the `AboutUs.jsx` file**, which includes details about the company. 

3. **Submit the GitHub URL of the `App.css` file**, which includes the background image for the **Paradise Nursery** landing page.

4. **Submit the GitHub URL of the `App.jsx` file**, which includes the **Paradise Nursery** landing page with the company\'s welcome message and a **\"Get Started\"** button.

5. **Submit the GitHub URL of the `CartSlice.jsx` file**, which includes the Redux slice for the shopping cart.
   - Ensure it defines Redux functionality to **add, remove, and update** cart items.

6. **Submit the GitHub URL of the `ProductList.jsx` file**, which implements the product listing page with the following functionalities:  
   - Display **at least six unique houseplants per category**, each with a thumbnail, name, and price.  
   - Group the plants into **at least three categories**.  
   - Include **\"Add to Cart\"** buttons that:  
     - Add the product to the cart.  
     - Disable the button after the item is added.  
     - Update the cart.
   - Include a **navbar** visible on both Product Listing and Cart pages, with links to **Home**, **Plants**, and **Cart**.  
   - Display a **cart icon** showing the **total number of items dynamically**.

7. **Submit the GitHub URL of the `CartItem.jsx` file**, which displays the **Shopping Cart page** with the following functionalities:  
   - Show the **total cart amount** for all plants.  
   - Display the **total cost per plant** in the cart.  
   - Each cart item should display the **thumbnail, plant name, and unit price**.  
   - Include buttons to **increase or decrease quantity**, updating totals correctly.  
   - Include a **delete button** to remove items from the cart.  
   - Include a **checkout button** that displays **\"Coming Soon\"** or a similar message.  
   - Include a **continue shopping button** that links back to the **Product Listing** page.

 **Before You Submit**
- Ensure all files are **updated, committed, and pushed** to the **`e-plantShopping`** repository.  
- Each submitted link must be a **public GitHub URL** pointing **directly to the specific file**.  
- Verify that all functionalities work correctly before final submission.  

# **Checklist for Option 2: Peer Review Evaluation**

After completing the final project, you should:

1. **Submit the URL of your deployed application**, hosted on **GitHub Pages** or another platform.  
   - Ensure your app is fully functional and **publicly accessible**.

2. **Submit the GitHub URL of your public repository**, named **`e-plantShopping`**.
   - Ensure all files are committed and pushed before submission.

**Project Evaluation Rubric for peer review**

**GitHub Link:**
- Public GitHub repository URL  
- Redux-related files and code implemented correctly  
	
**By URL of your deployed application:**
	
**Landing Page**
- Background image displayed properly  
- Includes a paragraph about the company  
- Displays the company name  
- Includes a \"Get Started\" button that links to the product listing page  

**Product Listing Page**
- Displays at least six unique houseplants for sale, each showing a thumbnail, name, and price  
- Groups plants into at least three categories  
- Includes an \"Add to Cart\" button for each plant that:  
  - Adds the selected plant to the shopping cart  
  - Increments the shopping cart icon count  
  - Disables the button after the plant is added  

 **Header**
- Displays on both the product listing and shopping cart pages  
- Includes a shopping cart icon that dynamically displays the total number of items  
- Allows navigation between the product listing and shopping cart pages  

 **Shopping Cart Page**
- Displays the total number of plants in the cart  
- Displays the total cost of all items  
- Each plant type displays a thumbnail, name, and unit price  
- Includes buttons to increase or decrease the quantity of each plant and update totals accordingly  - Includes a delete button to remove items from the cart  
- Includes a checkout button displaying \"Coming Soon\" or a similar message  
- Includes a \"Continue Shopping\" button linking back to the product listing page

	**Before You Submit**
- Confirm that your deployed application link opens correctly.
- Ensure your GitHub repository is public and includes all the latest updates.

#### Author
Richa Arora

## <h3 align="center"> &#169; IBM Corporation. All rights reserved. <h3/>

<!--
## Changelog
| Date | Version | Changed by | Change Description |
|------|--------|--------|---------|
| 2024-10-24 | 0.1 | Nikesh Kumar | Add code explanation for task 5 & 6 |
| 2025-02-13 | 0.2 | Rajashree Patil | For Task 3, added clear instructions, hints, code snippets, and removed point 7 & 8 as they were redundant and merged them in point 4,5,6  |
| 2025-05-01 | 0.3 | Alima Akhter | Changed folder structure screenshot and added inline comments in code snippets  |
| 2025-05-16 | 0.4 | Sapthashree | Updated the instructions Hints and also added the Github deployment in the hint section  |
|   |   |   |   |
-->