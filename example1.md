### Common Preparation Steps (Applies to Both Windows and Linux)
Before starting, you'll need to prepare the code and download CloudSim. These steps are the same on both OS:

1. **Download CloudSim**:
   - Go to the CloudSim GitHub releases page (search for "CloudSim 3.0.3 download" in your browser if needed).
   - Download the ZIP file for version 3.0.3 (or newer if available, but the code is tested with 3.0.3).
   - Extract the ZIP to a folder, e.g., `C:\cloudsim` on Windows or `~/cloudsim` on Linux.
   - Note the path to the JAR files inside, typically `cloudsim-3.0.3.jar` and `cloudsim-examples-3.0.3.jar` (you mainly need the core JAR).

2. **Prepare the Java Code**:
   - Create a new file named `SJFCloudSimExample.java` using any text editor (e.g., Notepad on Windows or nano/vim on Linux).
   - Copy-paste the provided program code into this file and save it in a working folder, e.g., `C:\cloud-experiment` on Windows or `~/cloud-experiment` on Linux.

3. **Choose Your Method**: You can run this using the terminal/command line (no IDE needed) or an IDE like Eclipse or IntelliJ. I'll explain both options for each OS.

Now, follow the OS-specific sections below to install Java, set up, and run the experiment.

### Steps for Windows
#### 1. Install Java JDK (if not already installed)
   - Download JDK 8 or higher from the Oracle website (oracle.com/java/technologies/downloads) or Adoptium (adoptium.net).
   - Run the installer (.exe file) and follow the prompts. Choose a version like JDK 17 for compatibility.
   - After installation, add Java to your PATH:
     - Right-click "This PC" > Properties > Advanced system settings > Environment Variables.
     - Under "System variables," find "Path" and edit it.
     - Add the path to the `bin` folder, e.g., `C:\Program Files\Java\jdk-17\bin`.
     - Click OK to save.
   - Verify: Open Command Prompt (search for "cmd") and type `java -version`. It should show the JDK version.

#### 2. Option A: Run Using Command Prompt (No IDE Needed)
   - Open Command Prompt and navigate to your working folder:
     ```
     cd C:\cloud-experiment
     ```
   - Compile the code, including the CloudSim JAR in the classpath (replace paths if different):
     ```
     javac -cp "C:\cloudsim\cloudsim-3.0.3.jar" SJFCloudSimExample.java
     ```
     - If there are errors, double-check the JAR path and code indentation.
   - Run the program:
     ```
     java -cp ".;C:\cloudsim\cloudsim-3.0.3.jar" SJFCloudSimExample
     ```
     - The output will appear in the Command Prompt, similar to the provided results (e.g., initialization messages, cloudlet outputs).

#### 3. Option B: Run Using an IDE (Eclipse Example)
   - Download and install Eclipse from eclipse.org (choose "Eclipse IDE for Java Developers").
   - Open Eclipse and create a new Java Project: File > New > Java Project. Name it "CloudSimExperiment".
   - Add your Java file: Right-click the "src" folder > New > Class. Paste the code into `SJFCloudSimExample.java`.
   - Add CloudSim JAR to classpath:
     - Right-click the project > Build Path > Configure Build Path > Libraries tab > Add External JARs.
     - Browse to `C:\cloudsim\cloudsim-3.0.3.jar` and add it.
   - Run: Right-click `SJFCloudSimExample.java` > Run As > Java Application.
   - Output will show in the Eclipse console.

#### Troubleshooting on Windows
- If JAR path has spaces, wrap it in quotes.
- Ensure no antivirus blocks Java.
- If VMs fail to create (as in sample output), it's normal due to resource limits in the simulation—results still generate.

### Steps for Linux (Assuming Ubuntu/Debian; Adjust for Other Distros Like Fedora)
#### 1. Install Java JDK (if not already installed)
   - Open Terminal (Ctrl+Alt+T).
   - Update packages: `sudo apt update`.
   - Install JDK: `sudo apt install openjdk-17-jdk` (for JDK 17; use `openjdk-8-jdk` if you want exactly JDK 8).
   - Verify: Type `java -version`. It should show the OpenJDK version.

#### 2. Option A: Run Using Terminal (No IDE Needed)
   - Open Terminal and navigate to your working folder:
     ```
     cd ~/cloud-experiment
     ```
   - Compile the code, including the CloudSim JAR in the classpath (replace paths if different):
     ```
     javac -cp ~/cloudsim/cloudsim-3.0.3.jar SJFCloudSimExample.java
     ```
     - If errors, check JAR path and code formatting (use `nano SJFCloudSimExample.java` to edit).
   - Run the program:
     ```
     java -cp .:~/cloudsim/cloudsim-3.0.3.jar SJFCloudSimExample
     ```
     - Note the colon `:` in the classpath (different from Windows' semicolon `;`).
     - Output will print in the Terminal, matching the sample (e.g., cloudlet execution details).

#### 3. Option B: Run Using an IDE (Eclipse Example)
   - Install Eclipse: In Terminal, `sudo apt install eclipse`.
   - Open Eclipse from the menu or Terminal (`eclipse`).
   - Create a new Java Project: File > New > Java Project. Name it "CloudSimExperiment".
   - Add your Java file: Right-click "src" > New > Class. Paste the code into `SJFCloudSimExample.java`.
   - Add CloudSim JAR to classpath:
     - Right-click project > Build Path > Configure Build Path > Libraries > Add External JARs.
     - Browse to `~/cloudsim/cloudsim-3.0.3.jar` and add it.
   - Run: Right-click `SJFCloudSimExample.java` > Run As > Java Application.
   - Output appears in the Eclipse console.

#### Troubleshooting on Linux
- Permissions: If JAR access denied, use `chmod +r ~/cloudsim/cloudsim-3.0.3.jar`.
- For other distros (e.g., Fedora): Use `sudo dnf install java-17-openjdk-devel` for JDK.
- If simulation shows VM creation failures, it's expected in the code—focus on the final cloudlet output.

### Running the Experiment and Analyzing Results
- On both OS, the simulation runs quickly (seconds).
- The output will list cloudlet details like ID, status, times—compare with defaults by modifying the code (e.g., remove the sort for FCFS).
- To experiment further: Edit cloudlet lengths or VM counts in the code, recompile, and rerun.
- If using a newer CloudSim version, check for API changes (e.g., class names) and adjust the code accordingly.
