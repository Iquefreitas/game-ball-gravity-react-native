# Falling Ball Simulation

This is a simple React Native application that simulates a ball falling under the influence of gravity. Users can interact with the application by applying an upward force to the ball, causing it to bounce.

## Technologies Used

* [React Native](https://reactnative.dev/)
* JavaScript

## Setup

To run this application on your local machine, you will need to have Node.js, npm (or yarn), and Expo CLI or a local React Native development environment set up.

1.  **Clone the repository** (if you have the code in a repository):
    ```bash
    git clone <repository-url>
    cd <project-directory>
    ```

2.  **Install dependencies:**
    Using npm:
    ```bash
    npm install
    ```
    or using Yarn:
    ```bash
    yarn install
    ```

3.  **Run the application:**
    If you are using Expo CLI:
    ```bash
    npx expo start
    ```
    This will open the Expo Go app on your simulator/emulator or physical device.

    If you are using a local React Native development environment, you might use commands like:
    ```bash
    npx react-native run-android
    # or
    npx react-native run-ios
    ```
    (depending on your target platform).

## How to Use

The application displays a ball that is constantly affected by gravity, causing it to fall.

* You will see a button labeled "Fazer Força" (Apply Force).
* Tapping or clicking this button will apply an upward force to the ball, making it move upwards against gravity.
* The application also displays real-time information about:
    * **UpForce:** The current upward force being applied to the ball.
    * **Speed:** The vertical speed of the ball.
    * **PosY:** The vertical position of the ball (0 being the bottom).

## Code Explanation

The main logic of the application resides in the `App.js` file:

* **State Variables:**
    * `gravity`: A constant representing the force of gravity.
    * `upForce`: The current upward force applied to the ball.
    * `speed`: The current vertical speed of the ball.
    * `posY`: The current vertical position of the ball.

* **`useEffect` Hook:** This hook runs on every render and is responsible for the animation loop. It does the following:
    * Calculates the new upward force by decreasing it by the gravity amount. It ensures `upForce` doesn't go below zero.
    * Calculates the new speed of the ball based on gravity and the current upward force.
    * Calculates the new vertical position of the ball based on its current position and speed.
    * Implements a basic collision detection with the bottom of the screen (`newPosY < 0`), resetting the position to 0 and the speed to 0 if the ball hits the bottom.
    * Uses `setTimeout` to create an animation loop, calling `applyGravity` every 30 milliseconds.

* **`handleForceButton` Function:** This function is called when the "Fazer Força" button is pressed. It sets the `upForce` to 7, causing the ball to move upwards.

* **JSX:** The return statement renders the user interface, which includes:
    * An `area` view to contain the `Ball` component.
    * A `control` view to display information and the "Fazer Força" button.
    * The `Ball` component, which likely handles the visual representation of the ball based on the `posY` state.

## Project Structure

The project structure includes the following files:

* `App.js`: Contains the main application logic and rendering.
* `./styles.js`: Likely contains the styling rules for the application components.
* `./components/Ball.js`: Contains the `Ball` component, responsible for rendering the ball.
* `./assets/powered-final.png`: An image asset used in the header.

## Further Development

Potential future enhancements could include:

* Adding visual elements to represent gravity and applied force.
* Implementing more realistic bouncing physics.
* Allowing the user to control the gravity.
* Adding different types of forces or obstacles.
* Improving the user interface and visual design.