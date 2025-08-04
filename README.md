# Smarter & Faster KYC: Real-Time Identity Verification

### **Introduction**

This project is a Proof-of-Concept for a serverless web application that automates the Know Your Customer (KYC) process. It leverages AWS AI services to perform real-time identity verification, including facial liveness detection, document data extraction, and face matching.

### **Key Features**

- **User Authentication:** Secure sign-up and sign-in via Amazon Cognito.
- **Document Upload:** A user-friendly interface for uploading identity documents.
- **Facial Liveness Check:** Browser-based verification using gestures to prevent spoofing.
- **AI-Powered Verification:** Integrates with Amazon Rekognition for face matching and Amazon Textract for OCR.
- **Serverless Architecture:** A scalable and cost-effective backend powered by AWS Lambda and other services.

### **Prerequisites**

To get this project running locally, you need to have the following installed:

- [**Git**](https://git-scm.com/downloads)
- [**Node.js**](https://nodejs.org/) (v18 or higher)
- [**Amplify CLI**](https://docs.amplify.aws/cli/start/install/) (v12.0 or higher) installed globally.
  - `npm install -g @aws-amplify/cli`
- An **AWS Account** with an IAM user configured for the Amplify CLI.

### **Setup Instructions**

Follow these steps to clone the repository and set up the project on your local machine.

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/[your-username]/[your-repo-name].git
    cd [your-repo-name]
    ```

2.  **Install dependencies:**

    - Navigate into the frontend folder, which is the root of your Amplify project:
      ```bash
      cd frontend
      ```
    - Install all dependencies for your frontend and backend:
      ```bash
      npm install
      ```

3.  **Connect to the Amplify Backend:**

    - Pull the Amplify backend configuration from the cloud. This command links your local project to the AWS resources. You must run this command from inside the `frontend` directory.
      ```bash
      amplify pull --appId d1shw6ymutgr0j --envName dev
      ```
    - You can find your `appId` in the Amplify Console.

4.  **Start the application:**

    - Start the local development server from within the `frontend` directory:
      ```bash
      npm run dev
      ```
    - Your application should now be running locally and connected to your AWS backend.

### **Collaboration Workflow**

To work on new features without disrupting other team members, follow this standard workflow:

1.  **Create a New Branch:** Before starting a new feature, create a new Git branch and switch to it.

    ```bash
    git checkout -b feature/your-new-feature-name
    ```

2.  **Add a New Amplify Environment:** Create a new Amplify backend environment that corresponds to your new branch. This gives you an isolated sandbox for your work.

    ```bash
    amplify env add
    ```

    Follow the prompts to name your new environment (e.g., `newfeature-dev`).

3.  **Deploy Your Isolated Environment:**

    ```bash
    amplify push
    ```

    This command will provision all the necessary backend resources for your new environment, and you can now develop on your new feature without affecting the main `dev` environment.

4.  **Merge and Clean Up:** When your feature is complete, merge your branch into `main`. Once merged, you can remove your temporary backend environment.

    ```bash
    amplify env remove newfeature-dev
    ```

### **Deployment**

- To deploy your changes to the cloud, use the following command from the `frontend` directory:
  ```bash
  amplify push
  ```
  This command will sync your local backend configuration with the **current active environment**.

### **Contributing**

- We welcome contributions\! Please fork the repository and submit a pull request for any new features or bug fixes. For major changes, please open an issue first to discuss what you would like to change.
- Please follow the existing code style and conventions.

---

### **License**

This project is licensed under the MIT License. See the `LICENSE` file for details.
