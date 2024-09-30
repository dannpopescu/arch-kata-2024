# ClearView| Architectural Kata

- Dan Popescu
- Chiris-Tocila
- Cornel Paun
- Valentina Gheorghe

# Company Overview

InnovateTalent Solutions is a cutting-edge software development company specializing in innovative talent management platforms. Our flagship product is an AI-driven recruitment application that reimagines the hiring process by offering a secure, anonymized presentation of candidate profiles to companies. This allows businesses to focus on skills and qualifications, ensuring an unbiased selection process.

Leveraging state-of-the-art artificial intelligence, our system automatically anonymizes candidate CVs by removing identifying information, such as names, photos, and contact details, while preserving key professional data. This approach fosters inclusivity and fairness, empowering companies to make data-driven hiring decisions. Additionally, the platform integrates seamlessly with corporate ATS systems, providing both scalability and flexibility for businesses of all sizes.

Our team is dedicated to pushing the boundaries of AI and cloud architecture, ensuring that our solutions remain scalable, efficient, and secure, all while maintaining a user-friendly experience for both candidates and employers.

At InnovateTalent Solutions, we believe in transforming the recruitment landscape by building trust, enhancing diversity, and promoting equal opportunities in the workplace.

# CleanView
Clear View is a supplemental HR platform that anonymizes candidate information while highlighting
objective skills and qualifying experience to reduce bias in the hiring process


It leverages AI to construct stories about a job candidate based on S.M.A.R.T (Specific, Measurable,
Achievable, Relevant, and Time-Bound) goals, qualifications, and experience, that are then quantifiably
aligned with open roles.


All personal identifiable information and characteristics are eliminated until an objective
determination is made on who the best candidate is to move forward with. The company pays to
unlock the profile and data points are aggregated to reveal any disparities between those who are
hired and those who were not selected.

## CleanView Requirements

### Functional Requirements
#### User Authentication and Profile Creation ####
- Support secure authentication methods (email, social media, or OAuth).
- Allow job seekers and recruiters to create profiles with relevant information (skills, experience, preferences).
- Support role-based access: job seekers, recruiters, and admins.

#### AI-Driven CV Anonymization ####
- Automatically detect and anonymize identifying information such as:
- Candidate’s name, contact details, and social media links.
- Profile photos and other personal images.
- Any data that can reveal identity (e.g., schools, certain location markers).
- Provide job seekers the ability to review and edit anonymized information before submission.

#### Candidate Profile Submission ####
- Allow candidates to upload CVs in various formats (PDF, Word, etc.).
- AI processes CV data and creates a structured profile (education, work experience, skills).
- Enable job seekers to choose which fields to anonymize before submission.

#### Recruiter Interface ####
- Provide recruiters with access to anonymized candidate profiles.
- Filter and search for candidates based on skillsets, experience, and job requirements.
- Allow recruiters to request additional information (post-anonymization) from candidates.

#### Matching and Recommendation System ####
- Match candidates with relevant job postings.
- Display anonymized profiles ranked by relevance to the recruiter’s job criteria.
- Notify candidates of suitable job opportunities based on their anonymized profiles. 

#### Company Feedback and Request System ####
- Enable recruiters to request partial or full de-anonymization for shortlisted candidates.
- Allow candidates to approve or deny de-anonymization requests.
- Collect feedback from companies to improve AI-based matching and anonymization.

#### Notifications and Communication ####
- Enable real-time communication between recruiters and candidates without revealing personal information.
- Notify candidates when recruiters request to view their non-anonymized data.

#### Data Security and Privacy Compliance ####
- Implement strict data privacy policies to comply with GDPR and other relevant data protection regulations.
- Ensure data encryption and secure storage of all CV and user information.
- Provide a clear data deletion policy for both candidates and recruiters.

### Non-Functional Requirements ###
#### Scalability ####

The system should handle high volumes of user registrations, CV submissions, and profile searches.
Plan for a system load of 5 million candidates and 1 million recruiters, with 100,000 daily active users.

#### Performance ####

Ensure AI-driven anonymization happens in real-time or within a maximum of 2 minutes per CV.
Ensure search and matching functionalities return results within seconds.

#### Availability ####

Ensure 99.9% uptime to support global recruiters and candidates.
Implement redundancy and failover mechanisms to maintain continuous operation.

#### Security ####

Use end-to-end encryption for data in transit and at rest.
Implement multi-factor authentication (MFA) for sensitive actions (profile creation, job application).

#### Usability ####

Provide a seamless, intuitive user interface for both job seekers and recruiters.
Ensure accessibility compliance (WCAG 2.1) for users with disabilities.

#### Maintainability ####

Ensure the codebase is modular and follows best practices for easy updates and maintenance.
Provide comprehensive API documentation for integration with third-party systems.

## Exploring components ##

### Choosing the architecture ###

We have three user facing components:
- Company Platform: used by the companies to see match results, unlock a resume or integrate an external HR System
- Candidate Platform: used by the candidates to see match results, upload or remove a resume
- Administrator Platform: used to generate reports, approve company enrollments

![Architecture](Infrastructure/images/overview.png)

