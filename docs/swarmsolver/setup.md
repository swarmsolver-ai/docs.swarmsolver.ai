# SwarmSolver Setup Guide

This guide will walk you through the steps to set up and run SwarmSolver on your local machine.

## Prerequisites

- **Java 17**: Ensure you have Java 17 installed on your system. You can download it from [AdoptOpenJDK](https://adoptopenjdk.net/) or [Oracle's Java SE](https://www.oracle.com/java/technologies/javase-jdk17-downloads.html).

## Installation

1. **Download SwarmSolver**:
    - You can download the latest release of SwarmSolver from the [GitHub releases page](https://github.com/swarmsolver-ai/swarmsolver/tags).

2. **Extract the Archive**:
    - Unzip the downloaded package to your desired installation directory.

## Configuration

### Setting Up Workspaces

Before running SwarmSolver, you need to configure your workspaces in the `application.yaml` file located in the extracted directory. You can also set the server port in this file.

1. **Open the `application.yaml` File**:
    - Use a text editor to open the file.

2. **Define Your Workspaces and Server Port**:
   - There is a default workspace structure in the unzipped package. it is recommended that you copy this initial workspace in a directory of your choice and refer to it from the `application.yaml`
    - Customize the workspaces and server port according to your needs. Here’s an anonymized example:

   ```yaml
   server:
     port: 8088

   ai.swarmsolver:
     workspaces:
       ProjectAlpha: /path/to/your/workspaces/ProjectAlpha
       ProjectBeta: /path/to/your/workspaces/ProjectBeta
   ```

    - **Server Port**: The `port` setting under `server` specifies the port number on which SwarmSolver will run. The default port is 8088, but you can change it to any available port number if needed.
    - **Workspaces**: Under `ai.swarmsolver`, you define the workspaces with their respective paths. Replace the example paths with the actual paths where your workspace data is stored.

## Additional Steps

1. **Copy Default Workspace Structure**:
   - When create a new workspace copy the directory structure from the default workspace. A workspace has the following structure:
     ```
     <workspace dir>
     ├── config
     │   ├── keys.properties
     │   └── agents.groovy
     └── data
     ```

2. **Get OpenAI API Key**:
   - The default agent defined in agents.groovy uses the OpenAI API
   - Obtain an OpenAI API key from OpenAI and paste it into the `keys.properties` file in the `config` directory. The entry for the key should be in the format: `OPENAI_API_KEY=sk-...`.

With these additional steps, your SwarmSolver setup will be complete and ready to run.
## Running SwarmSolver

### On Linux

1. **Make the `run.sh` Script Executable**:
    - Navigate to the directory where you extracted SwarmSolver.
    - Run the following command to make the script executable:
      ```bash
      chmod +x run.sh
      ```

2. **Run the Application**:
    - Execute the script to start SwarmSolver:
      ```bash
      ./run.sh
      ```

### On Windows

1. **Run the `run.bat` Script**:
    - Double-click the `run.bat` file located in the extracted directory to start SwarmSolver.
