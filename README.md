## Semantic Job Agent
From Job Matching to Intelligent Career Assistance.

## Summary
Semantic Job Agent is an AI-powered assistant designed to improve the way people search for jobs.
Instead of relying only on keywords and job titles, it analyses a candidate's professional experience, skills and competencies to identify job opportunities that are genuinely relevant, including opportunities that might otherwise be overlooked by traditional job-search systems.
Note: The system should always support human decisions, not replace them.

## Background
After more than 27 years in IT, I realised that traditional job-matching approaches do not always recognise the value of a professional background that has evolved over time.
My idea is to use AI to go beyond simple keyword matching and help people discover opportunities based on what they can actually do, rather than just on their previous job titles.
I have experienced this problem during my own job search. Finding a new job can be a challenging and time-consuming process. Most job platforms rely heavily on keywords, job titles and predefined filters.
As a result, candidates may miss interesting opportunities simply because their professional experience is described differently from the requirements in a job advertisement.
This is particularly relevant for professionals with many years of experience, who may have developed transferable skills across different roles, industries and technologies.
For example, someone who has worked as a software developer, business analyst, team leader and project manager may have competencies that are relevant to several different positions, even when the job title does not exactly match their previous experience.

## How is it used?
The candidate uploads their CV in PDF format.
The system analyses the document and creates a professional profile containing skills, experience, seniority, languages and other relevant information.
The application then retrieves job advertisements from external job-search platforms and compares them with the candidate's profile.
For each job opportunity, the system provides:
*	A matching score indicating how relevant the opportunity is.
*	A list of matching skills and competencies.
*	A list of skills or requirements that may be missing.
*	An AI-generated assessment explaining the strengths and possible gaps between the candidate's profile and the job requirements.
The goal is not to decide whether someone should apply for a job, but to provide better information and help candidates make more informed decisions.

## Data sources and AI methods
The project uses two main sources of information:
1.	Candidate data: information extracted from the CV uploaded by the user.
2.	Job advertisements: job descriptions retrieved through APIs. New system integrations could be added in the future.

The current implementation combines different techniques:
*	Natural Language Processing: to extract and structure relevant information from CVs and job descriptions.
*	Sentence embeddings: using the Sentence Transformers all-MiniLM-L6-v2 model to represent professional profiles and job descriptions as numerical vectors.
*	Semantic similarity: using cosine similarity to compare the meaning of candidate profiles and job descriptions, even when they use different words.
*	Skill matching: to identify matching and missing competencies.
*	Weighted ranking: combining semantic similarity (60%) and skill matching (40%) to calculate an overall matching score.
*	Generative AI: using a locally running Llama 3.1 model through Ollama to provide a qualitative explanation of the match.

## Challenges
One of the main challenges is understanding the meaning of professional experience rather than simply identifying keywords. Two job descriptions may use different terminology while requiring very similar competencies. Another challenge is determining how to evaluate transferable skills and distinguish between skills explicitly mentioned in a CV and competencies that can reasonably be inferred from previous experience. The matching score also needs further validation. A high semantic similarity score does not necessarily mean that a candidate is suitable for a position. Factors such as seniority, industry knowledge, responsibilities and personal preferences must also be considered.
Another important challenge to include is protecting personal information contained in CVs.

## What next?
I would like to improve it in several areas:
1.	Semantic matching by considering seniority, years of experience, responsibilities and industry knowledge.
2.	Add application tracking, including job applications, interviews and feedback.
3.	Generate tailored CVs and cover letters based on specific job opportunities.
4.	Develop an AI career assistant able to suggest professional development paths and identify skills gaps.
My idea for the future is to evolve Semantic Job Agent from a job-matching application into an intelligent career assistant that helps people understand their professional value and make better career decisions.

## Acknowledgments
I would like to thank the University of Helsinki for the “Elements of AI” course which provided me with the concepts and inspiration to explore how artificial intelligence can be applied to a real-world problem. Special thanks go to the developers and communities behind the open-source technologies and services used in this project, without which I would not have been able to develop this prototype.
