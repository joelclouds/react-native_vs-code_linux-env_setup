# react-native_vs-code_linux-env_setup
steps to setup linux env with vscode to build, emulate, test and deploy a react native app


**1. Prerequisites**

* **Node.js and npm:**
    * Install Node.js and npm using your distribution's package manager:
        ```bash
        sudo apt update
        sudo apt install nodejs npm 
        ```
    * Verify installation:
        ```bash
        node -v 
        npm -v
        ```

* **Java Development Kit (JDK):**
    * Install the OpenJDK:
        ```bash
        sudo apt install openjdk-11-jdk 
        ```
    * Verify installation:
        ```bash
        java -version
        ```

* **Android SDK:**
    * **Download:** Download the Command-line Tools only from the Android SDK website.
    * **Extract:** Extract the downloaded archive to a suitable location (e.g., `/opt/android-sdk`).
    * **Set Environment Variables:**
        * Open your terminal and edit your `.bashrc` file:
            ```bash
            nano ~/.bashrc
            ```
        * Add the following lines:
            ```bash
            export ANDROID_HOME=/opt/android-sdk 
            export PATH=$ANDROID_HOME/cmdline-tools/tools/bin:$ANDROID_HOME/cmdline-tools/latest/bin:$PATH
            ```
        * Save and close the file.
        * Apply the changes:
            ```bash
            source ~/.bashrc
            ```
    * **Install required packages:**
        ```bash
        cd $ANDROID_HOME/cmdline-tools/latest/bin/
        ./sdkmanager "platforms;android-33" "build-tools;33.0.1" "emulator" 
        ``` 
        (Replace with the latest stable Android version and build-tools)

* **VS Code:**
    * Install VS Code from the official website or using your distribution's package manager.

**2. Project Setup**

* **Create a React Native Project:**
    ```bash
    npx react-native init MyReactNativeApp 
    ```

* **Open in VS Code:**
    ```bash
    code MyReactNativeApp
    ```

**3. Install VS Code Extensions**

* **React Native Tools:**
    * Search for "React Native Tools" in the VS Code Extensions marketplace and install it.

* **Prettier - Code formatter** and **ESLint:** (Install as mentioned in the previous response)

**4. Run and Test**

* **Create an Android Emulator:**
    * **Install an Android emulator:** You can use the included emulator with the Android SDK or a third-party emulator like Genymotion.
    * **Start the emulator:** Start the emulator from the Android SDK command-line tools or the emulator's GUI.

* **Run the App:**
    * In the VS Code terminal, execute:
        ```bash
        npx react-native run-android 
        ```

**5. Debugging**

* **Use the React Native Tools debugger** within VS Code to set breakpoints, step through code, and inspect variables.

**6. Deployment (Basic)**

* **Build a Release APK:** Follow the steps outlined in the previous response, ensuring the correct paths for your Android SDK installation.

**Important Notes:**

* **Environment Variables:** Ensure the `ANDROID_HOME` environment variable is correctly set.
* **Emulator Setup:** Configure your emulator with sufficient resources (RAM, storage) for optimal performance.
* **Linux Distributions:** These instructions are general. Specific commands and installation steps might vary slightly depending on your Linux distribution (e.g., Ubuntu, Debian, Fedora).
* **Refer to Official Documentation:** Always refer to the official React Native documentation for the most up-to-date and accurate information.

By following these steps, you should be able to successfully set up your React Native development environment on Linux using VS Code.
