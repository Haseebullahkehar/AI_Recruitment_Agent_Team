# AI Recruitment System

## Overview

The **AI Recruitment System** is a Streamlit-based application designed to automate the recruitment process for technical roles. It leverages AI to analyze resumes, provide feedback, and schedule interviews. The system supports three main roles: **AI/ML Engineer**, **Frontend Engineer**, and **Backend Engineer**. It integrates with **OpenAI's GPT-4** for resume analysis, **Zoom** for interview scheduling, and **Email Tools** for communication with candidates.

## Features

1. **Resume Analysis**:
   - Upload a PDF resume.
   - The system extracts text from the resume and analyzes it against the required skills for the selected role.
   - Provides detailed feedback on the candidate's skills, including matching and missing skills.

2. **Email Communication**:
   - Sends automated emails to candidates based on the analysis results.
   - **Selection Email**: Congratulates selected candidates and provides next steps.
   - **Rejection Email**: Provides constructive feedback to rejected candidates, encouraging them to upskill and reapply.

3. **Interview Scheduling**:
   - Automatically schedules interviews using Zoom.
   - Interviews are scheduled during business hours (9 AM - 5 PM PKT).
   - Sends interview details to the candidate via email.

4. **Role-Specific Requirements**:
   - The system has predefined skill requirements for each role:
     - **AI/ML Engineer**: Python, PyTorch/TensorFlow, Machine Learning, Deep Learning, MLOps, etc.
     - **Frontend Engineer**: React/Vue.js/Angular, HTML5, CSS3, JavaScript/TypeScript, etc.
     - **Backend Engineer**: Python/Java/Node.js, REST APIs, Database design, Cloud services, etc.

5. **Session Management**:
   - The application maintains session state to store user inputs, resume text, and analysis results.
   - Allows users to reset the application and start over.

## Installation

### Prerequisites

- Python 3.8 or higher
- Streamlit
- PyPDF2
- Requests
- Pytz
- OpenAI API key
- Zoom account credentials (Account ID, Client ID, Client Secret)
- Email credentials (Sender email, App password)

### Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-repo/ai-recruitment-system.git
   cd ai-recruitment-system
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**:
   - Create a `.env` file in the root directory and add the following:
     ```plaintext
     OPENAI_API_KEY=your_openai_api_key
     ZOOM_ACCOUNT_ID=your_zoom_account_id
     ZOOM_CLIENT_ID=your_zoom_client_id
     ZOOM_CLIENT_SECRET=your_zoom_client_secret
     EMAIL_SENDER=your_email
     EMAIL_PASSKEY=your_email_passkey
     COMPANY_NAME=your_company_name
     ```

4. **Run the Application**:
   ```bash
   streamlit run main.py
   ```

## Usage

1. **OpenAI API Key**:
   - Enter your OpenAI API key in the sidebar.

2. **Zoom Credentials**:
   - Provide your Zoom Account ID, Client ID, and Client Secret in the sidebar.

3. **Email Settings**:
   - Enter the sender email, app password, and company name in the sidebar.

4. **Role Selection**:
   - Select the role you're applying for from the dropdown menu.

5. **Upload Resume**:
   - Upload a PDF resume. The system will extract and analyze the text.

6. **Candidate Email**:
   - Enter the candidate's email address.

7. **Analyze Resume**:
   - Click the "Analyze Resume" button to start the analysis process.

8. **Next Steps**:
   - If selected, proceed with the application to schedule an interview.
   - If rejected, the system will send a feedback email with suggestions for improvement.

9. **Reset Application**:
   - Use the "Reset Application" button in the sidebar to clear all inputs and start over.

## Code Structure

- **CustomZoomTool**: Extends the `ZoomTool` class to handle Zoom OAuth token management.
- **ROLE_REQUIREMENTS**: A dictionary containing the required skills for each role.
- **init_session_state**: Initializes session state variables.
- **create_resume_analyzer**: Creates an agent for resume analysis.
- **create_email_agent**: Creates an agent for handling email communications.
- **create_scheduler_agent**: Creates an agent for scheduling interviews using Zoom.
- **extract_text_from_pdf**: Extracts text from a PDF resume.
- **analyze_resume**: Analyzes the resume against the role requirements.
- **send_selection_email**: Sends a selection email to the candidate.
- **send_rejection_email**: Sends a rejection email with feedback.
- **schedule_interview**: Schedules an interview using Zoom and sends the details via email.
- **main**: The main function that runs the Streamlit application.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeatureName`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeatureName`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **OpenAI** for providing the GPT-4 model.
- **Streamlit** for the web application framework.
- **Zoom** for the API integration.
- **PyPDF2** for PDF text extraction.

## Contact

For any questions or issues, please open an issue on the GitHub repository or contact the maintainer directly.

---

**Note**: This is a simplified version of the README. You may want to add more details, such as screenshots, additional setup instructions, or troubleshooting tips, depending on your audience.
