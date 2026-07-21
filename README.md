# Audio Speech To Sign Language Converter

A Web Application which takes in live audio speech recording as input, converts it into text and displays the relevant Indian Sign Language animations.

> - Front-end using HTML,CSS,JavaScript.
> - Speech recognition using JavaScript Web speech API.
> - Text Preprocessing using Natural Language Toolkit(NLTK).
> - A 3D animation of a character created
>   using Blender 3D tool.

Project Demo Video: https://youtu.be/YiHhD0QGrno

## Prerequisites

> - Python >= 3.7
> - Browser supports Web Speech API
> - Download all required packages for python script A2SL/views.py

## Installation Guide:

These instructions will get you download the project and running on your local machine for development and testing purposes.

### Instructions

1. Open the Downloads folder and then open the terminal.
2. From the terminal, run the python file using the command "python manage.py runserver ####" (#### optional port number).
3. From the terminal, it shows localhost address (looks like this "server at http://127.0.0.1:8000/") run on browser.
4. Sign up and start exploring.
5. Click on mic button to record speech.
6. Speech is going to processed and respective animated outputs are shown accordingly and it also support entered text manually.
A real-time web application that converts spoken language and text into Indian Sign Language (ISL) animations, making digital communication more accessible for the deaf and hard-of-hearing community.
Table of Contents

Overview
Features
Technology Stack
Installation
Usage
Project Structure
API Documentation
Contributing
Roadmap
License
Acknowledgments

Overview
The Live Audio to Sign Language Converter addresses communication barriers between hearing and deaf communities by providing instant translation of speech and text into Indian Sign Language animations. The system combines modern web technologies with natural language processing to deliver grammatically accurate sign language representation through realistic 3D animations.
Problem Statement

Limited availability of sign language interpreters
High costs of professional interpretation services
Lack of real-time communication tools for deaf individuals
Insufficient accessibility in educational and public services

Solution
A free, web-based platform that:

Converts live speech to sign language animations
Processes text input for sign language output
Provides grammatically accurate translations
Works across all modern web browsers
Requires no app installation or special hardware

Features
Core Functionality

Real-time Speech Recognition: Uses JavaScript Web Speech API for continuous audio capture
Text Input Support: Manual text entry with instant processing
Intelligent NLP Processing: Grammar analysis, tense detection, and linguistic transformation
3D Sign Language Animations: High-quality Blender-created ISL gestures
Fallback System: Character-level fingerspelling for unknown words
Cross-platform Compatibility: Works on desktop, tablet, and mobile devices

Advanced Features

Grammatical Structure Preservation: Proper tense markers and temporal indicators
Stopword Filtering: Optimized for sign language communication patterns
Animation Sequencing: Smooth transitions between gestures
User Session Management: Conversation history and preferences
Responsive Design: Adaptive interface for various screen sizes
Accessibility Compliance: Screen reader support and keyboard navigation

Technology Stack
Backend

Python 3.8+: Core programming language
Django 4.0+: Web framework for robust application architecture
NLTK: Natural Language Processing library
SQLite/PostgreSQL: Database management
Django REST Framework: API development (optional)

Frontend

HTML5: Modern semantic markup
CSS3: Responsive design and animations
JavaScript ES6+: Interactive user interface
Web Speech API: Browser-based speech recognition
Bootstrap/Tailwind CSS: UI framework (optional)

3D Animation

Blender: 3D modeling and animation creation
MP4/WebM: Video formats for web compatibility
FFmpeg: Video processing and optimization

Development Tools

Git: Version control
Visual Studio Code: Development environment
Chrome DevTools: Debugging and testing

Installation
Prerequisites
# Python 3.8 or higher
python --version

# pip package manager
pip --version

# Git for cloning repository
git --version

Clone Repository
bashgit clone https://github.com/yourusername/live-audio-sign-language-converter.git
cd live-audio-sign-language-converter
Virtual Environment Setup
bash# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
Install Dependencies
bash# Install Python packages
pip install -r requirements.txt

# Download NLTK data
python -c "import nltk; nltk.download('punkt'); nltk.download('averaged_perceptron_tagger'); nltk.download('wordnet')"
Database Setup
bash# Run migrations
python manage.py makemigrations
python manage.py migrate

# Create superuser (optional)
python manage.py createsuperuser
Static Files Setup
bash# Collect static files
python manage.py collectstatic
Run Development Server
bashpython manage.py runserver
Visit http://127.0.0.1:8000 to access the application.

Usage
Basic Operation

Access the Application

Open your web browser
Navigate to the application URL
Allow microphone permissions when prompted


Speech Input

Click the microphone button
Speak clearly into your microphone
Watch real-time speech recognition
View generated sign language animation


Text Input

Use the text input field as an alternative
Type your message and press Enter
System processes and displays sign language


Animation Playback

Animations play automatically after processing
Use playback controls for replay/pause
Adjust playback speed if needed



Advanced Features
Grammar Processing
The system intelligently processes grammatical structures:
Input: "I was eating dinner"
Processing: Tense detection → Past tense
Output: "Before I eat dinner" (with temporal marker)
Fallback System
For unknown words, the system provides fingerspelling:
Input: "Cryptocurrency"
Processing: Word not in database
Output: Individual letter animations (C-R-Y-P-T-O...)
Project Structure
live-audio-sign-language-converter/
│
├── manage.py                 # Django management script
├── requirements.txt          # Python dependencies
├── README.md                # Project documentation
│
├── sign_language_app/       # Main Django application
│   ├── models.py           # Database models
│   ├── views.py            # View controllers
│   ├── urls.py             # URL routing
│   ├── forms.py            # Form handling
│   └── utils/              # Utility modules
│       ├── speech_processor.py
│       ├── nlp_processor.py
│       └── animation_manager.py
│
├── templates/              # HTML templates
│   ├── base.html
│   ├── index.html
│   └── components/
│
├── static/                 # Static files
│   ├── css/
│   ├── js/
│   │   ├── speech-recognition.js
│   │   ├── animation-player.js
│   │   └── main.js
│   └── animations/         # Sign language video files
│       ├── words/
│       └── letters/
│
├── media/                  # User-uploaded content
├── config/                 # Django settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
└── docs/                   # Additional documentation
    ├── api.md
    ├── deployment.md
    └── contributing.md
API Documentation
Speech Processing Endpoint
httpPOST /api/process-speech/
Content-Type: application/json

{
    "text": "Hello, how are you?",
    "language": "en-US"
}

Response:
{
    "processed_text": "Hello how you",
    "animations": ["hello.mp4", "how.mp4", "you.mp4"],
    "status": "success"
}
Animation Retrieval
httpGET /api/animations/{word}/
Response: Video file or fallback to character spelling
Contributing
We welcome contributions from the community! Here's how you can help:
Areas for Contribution

Animation Creation: Expand the ISL vocabulary database
Language Processing: Improve NLP accuracy and grammar handling
User Interface: Enhance accessibility and user experience
Testing: Add unit tests and integration tests
Documentation: Improve code documentation and user guides

Development Workflow

Fork the repository
Create a feature branch (git checkout -b feature/new-feature)
Make your changes
Add tests for new functionality
Ensure all tests pass
Commit your changes (git commit -m 'Add new feature')
Push to the branch (git push origin feature/new-feature)
Create a Pull Request

Code Standards

Follow PEP 8 for Python code
Use meaningful variable and function names
Add docstrings for all functions and classes
Include unit tests for new features
Maintain backward compatibility

Roadmap
Phase I (Current) - Core Functionality

 Basic speech recognition integration
 NLP processing pipeline
 Animation playback system
 Web interface development
 Django backend architecture

Phase II - Enhancement

 Expand animation vocabulary (500+ words)
 Improve animation quality and realism
 Add user authentication and profiles
 Implement caching for better performance
 Mobile app development

Phase III - Advanced Features

 Multiple sign language support (ASL, BSL, etc.)
 Real-time conversation mode
 Sign language to text conversion
 Integration with video calling platforms
 Machine learning for animation generation

Phase IV - Community & Scale

 Community contribution system
 Regional sign language variations
 Educational institution partnerships
 API for third-party integrations
 Cloud deployment and scaling

Deployment
Development Environment
bashpython manage.py runserver
Production Deployment
Using Gunicorn and Nginx
bash# Install production dependencies
pip install gunicorn

# Run with Gunicorn
gunicorn config.wsgi:application --bind 0.0.0.0:8000
Docker Deployment
bash# Build Docker image
docker build -t sign-language-converter .

# Run container
docker run -p 8000:8000 sign-language-converter
Cloud Platforms

Heroku: Ready for one-click deployment
AWS: EC2 instance with load balancer
Google Cloud: App Engine deployment
DigitalOcean: Droplet with automated setup

Performance Optimization
Frontend Optimization

Lazy loading for animation files
Browser caching strategies
Compressed asset delivery
Progressive web app features

Backend Optimization

Database query optimization
Redis caching implementation
Asynchronous task processing
CDN integration for static files

Security Considerations

HTTPS enforcement for voice data
CSRF protection for form submissions
Input validation and sanitization
Rate limiting for API endpoints
Regular security updates

Testing
Run Tests
bash# Run all tests
python manage.py test

# Run specific test module
python manage.py test sign_language_app.tests.test_nlp_processor

# Run with coverage
coverage run manage.py test
coverage report
Test Categories

Unit tests for NLP processing
Integration tests for speech recognition
Frontend testing with Selenium
Performance testing for animation loading

Troubleshooting
Common Issues
Speech recognition not working:

Ensure microphone permissions are granted
Check browser compatibility (Chrome recommended)
Verify stable internet connection

Animations not loading:

Check static file configuration
Verify animation file formats (MP4/WebM)
Clear browser cache

Slow performance:

Enable caching in Django settings
Optimize animation file sizes
Check network connectivity



NLTK Team: For comprehensive natural language processing tools
Django Community: For the robust web framework
Blender Foundation: For 3D animation capabilities
Web Speech API Contributors: For browser-based speech recognition
Indian Sign Language Community: For guidance and validation
Academic Supervisors: For project guidance and support

Citations
  title=Live Audio to Sign Language Converter using NLP,
  author= ABISHEK P,
  year=2025-2026,
  url=https://github.com/Abishek77sist/live-audio-to-sign-language-using-natural-language-processing

Contact

Developer: ABISHEK P
Email: abishek050205@example.com
Institution: Sathyabama institute of science and technology
Project Guide: Dr. M P Vaishnavee

Support
If you encounter issues or have questions:

Check the troubleshooting section
Search existing GitHub Issues
Create a new issue with detailed description
Join our community discussions


Made with ❤️ for the deaf and hard-of-hearing community