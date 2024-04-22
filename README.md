# testrepo_2024-04-22_1103


---

# Project: Creation of Test Cases for Ideal and Non-Ideal Behaviors in GitHub Repositories

## Description

This project aims to create a comprehensive set of test cases for GitHub repositories, covering both ideal and non-ideal behaviors. By generating random sample data that adheres to specified rules as well as data that violates these rules, the project assesses the effectiveness and accuracy of the "detection-of-ideal-behaviours-with-low-impact-in-github-repositories" tool. This tool evaluates various scenarios within GitHub repositories to ensure their functionality, reliability, and security.

The Criteria for creating testcases based on the following rules are below

---

```
{
    "rules" : {
        /*
            Some notes: An important term here is "meaningful". Our goal with this project is to find people who are not making meaningful contributions.
            The meaningful threshold below defines the number of lines of code that the commit must contain in order to be considered meaningful.
            All numbers below are placeholders/defaults. Remember that a manager should be able to edit these to their liking/needs.
            Finally, a 0 or "" value means that rule should be skipped.
        */
        "meaningfulLinesThreshold" : 5, // The minimum number of (non-comment) lines a commit must have in order to be considered meaningful
        "minCommits" : 3, // The minimum number of meaningful commits a developer is expected to make
        "minLines" : 0, // The minimum number of lines of code the developer is expected to have added overall
        "maxBranches" : 2, // The maximum number of different branches the developer is expected to commit to
        "minTimeBetweenCommits" : 2, // The minimum amount of time (in hours) a developer is expected to wait between making commits (rapid fire commits are suspicious)
        "maxFilesPerCommit" : 3, // The maximum number of files a developer is expected to edit per commit
        /*
            Branches in the validBranches list are ones that you should consider when applying the rules. This allows developers to perform operations in test branches
            without being flagged. Likewise, if they only commit in invalid branches, that should be flagged as they have not made commits on the required branches.
            If the list is empty, you should apply the rules to their commits on all branches.
        */
        "validBranches" : [
            "main",
            "development"
        ],
        "numAllowedDuplicateCommitsOnDifferentBranches" : 0, // This is how many times a developer can make an identical commit on different branches
        "allowedFileTypes" : [ // Which file types developers are expected to commit - if blank allow all file types
            ".java"
        ],
        "minPRToCreate" : 1, // The minimum number of Pull Requests (PR) that a developer is expected to make in a sprint
        "maxTimeToReviewPR" : 24, // The max time (in hours) from when a PR is opened until it is closed (the assignee is the user to flag if this is violated)
        "maxIssuesOpened" : 5, // If a user opened more than this many issues during the sprint, flag it as a potential issue
        "maxTimeToResolveIssue" : 24 // The max time (in hours) from when an issue is opened until it is closed (the assignee is the user to flag if this is violated)
    }
}
```

---



## Installation

### Prerequisites

- Python 3.1.23 or later installed on your system
- Basic understanding of using the command line
- The Github Account shouldn't have any form of extreme Authentication while login

### Steps

1. **Install Python:** Download and install Python from the [official Python website](https://www.python.org/downloads/release/python-3123/).

2. **Add Python to Path:** During installation, make sure to add Python to the system path for global accessibility.

3. **Download Project:** Clone or download the project repository to your local computer.

4. **Create Virtual Environment:** Open your terminal or command prompt, navigate to the project directory, and create a virtual environment using Python's venv module. Example:
   ```bash
   python3 -m venv venv
   ```

5. **Activate Virtual Environment:** Activate the virtual environment. On Windows:
   ```bash
   venv\Scripts\activate
   ```
   On macOS/Linux:
   ```bash
   source venv/bin/activate
   ```

6. **Install Dependencies:** With the virtual environment activated, install the required packages using pip:
   ```bash
   pip3 install -r requirements.txt
   ```

7. **Installation Complete:** You have successfully installed the project and its dependencies.

## Usage

1. **Start Server:** Navigate to the project directory in your terminal and run the following command to start the server:
   ```bash
   python3 app.py
   ```

2. **Access Form:** Open your web browser and go to [http://127.0.0.1:8000](http://127.0.0.1:8000) to access the form.

3. **Fill Form:** In the form, enter the required information such as username, email, and tokens based on the number of collaborators. Leave fields blank or enter 0 to exclude rules from evaluation.

4. **Submit Form:** Click the Submit button in the form to initiate the script.

5. **Script Execution:** The script will run in the console, prompting you to perform actions such as accepting invites in emails or GitHub.

6. **View Results:** Once all collaborators have accepted invites, the script will generate test cases and print details including any detected violations.

7. **Completion:** The server will automatically reload or the web page will stop loading once the script completes its execution.

## Contributing

If you'd like to contribute to this project, please follow these guidelines:

- Fork the repository and create a new branch for your contributions.
- Make your changes and ensure they adhere to coding standards.
- Submit a pull request detailing your changes and improvements.

## License

This project is licensed under the [MIT License](LICENSE), which allows for free use, modification, and distribution.

---

