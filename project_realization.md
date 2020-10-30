# Progress Report (10.28.2020)
## Overview
For the duration of this semester, our team has utilized a private Slack channel for communication, the GitHub issue tracker, and Projects section to create a sprint plan. This was our initial effort to organize and plan for our research, testing, and establishing the neccessary work environments. Our initial efforts included finding the best ways to test exactly what was being captured or harvested from a Facebook user's profile image upload. We wanted to infer from the user interface behavior and a passive network traffic capture, the accuracy of photo tagged uploads and any user data that might've been harvested from those uploads.

Our efforts have shifted to be focused on the analyzing of Facebook's open source coding libraries, observing the behavior of Facebook's facial recognition feature, utilizing the Postman API for HTTP method captures, and training the coding algorithms with different test model loads to draw conclusions about potential privacy implications. 

We have took on tasks in groups of two, to help compare observations, testing, and results. Specifically, each of us have spent time focused on individual pieces of work while collaborating wholy on our milestone. With our efforts invested, our previous testing wasn't as significant as we had hoped. Nonetheless, we were consistent in digging for information and asking questions with what results we did obtain. Going forward, our efforts will be zoned in on our chosen code algorithms from Facebook's open source libraries and any implications regarding facial recognition, bias, and privacy.

## Outcomes
*<b> Outcome 1</b>: We started by packet capturing the network traffic on Facebook using Wireshark to discern if any user data that should not be obtained from Facebook was harvested. We were able to decrypt the TCP packet information from Wireshark by following the stream that tells us what is being sent over the network. The information yielded browser information that was inconclusive. We acheived only the browser data of what the image upload sent to Facebook's servers.

*<b> Outcome 2</b>: We have initiated a HTTP method capture in Postman instead that will yield more useful information that is easier to interpret. (NEED CAROLINE's RESULTS HERE)

*<b> Outcome 3</b>: We wanted to test the user interface to discern if the auto-tagging feature would provide any insight to misuse behavior or poor accuracy in user media uploads. This included a false auto-tag of not properly tagging a user who has uploaded a photo of themselves along with not tagging that specific user's friends in a photo when uploaded as well. The effort made in these areas has shown to be trivial due to the user interface behavior behaving according to the user's settings. We are doing extensive testing on the accuracy of this behavior. Overall, we acheieved/concluded that the accuracy of this behavior is due to a bias that Facebook has implemented through their coding algorithms. Certain data inputs (user photo uploads) do not get tagged properly (auto or manual) depending on gender or race as well as if the user has a brand new account with not enough data points for Facebook's AI to understand yet.

*<b> Outcome 4</b>: We achieved the proper way to conduct our environment setup with hopes of testing DeepMask and MultiPath networks.

working test environment after numerous attempts to get the setup working. The challenges presented included working through multiple interdependencies that all correlated to successful test conditions.

*<b> Outcome 5</b> To collect the input infromation provided by the user to Facebook when uploading images. Here is the HTTP request captured by Postman app on a Facebook upload. [Upload Capture](https://www.getpostman.com/collections/8cece61b74a2db5e8aaf).

## Hinderances
Our challenges included miscommunication in regard to how we wanted to obtain the implications for privacy. We believed our goals would be best tackled by analyzing the code libraries to see what inputs Facebook was taking and testing by observing the UI and packet captures to review the accuracy of the data information. Other challenges we face included multiple attempts to get a working test environment, combing through a Postman capture to retrieve the HTTP method capture details, having our Facebook test accounts be deactivated or banned. For work environment, we had to find the correct versions for Torch librady, CUDA toolkit, and Ubuntu operating system that work together. This also includes modifying source code before building the environment to circumvent issues with different dependencies.

## Ongoing Risks
|Risk Name  | Impact     | Likelihood | Description | Mitigation | Updates |
|-------------------|------------|------------|-------------|-------------|---------|
|Team Member Availability (28) | 7 | 4 | Aligning meeting times around academic and work schedules may deem difficult | Plan is to meet each week after weekly check-ins with Dr. Hale until an issue may arise | Members have been available weekly to address project needs |
|Communication/Under communication (24) | 8 | 3 | If any requirements are misinterpreted by the project team a gap develops between expectations, requirements and milestones | May need to communicate the same idea many times in different ways before people remember it | Miscommunication has been the biggest downfall for our team, we have not been able to complete our projects goals to our expectations due to this |
|Software Availability (27) | 9 | 3 | Not all of the necessary software for analysis may be open source | Work around would be to check UNO's available software for students or low cost subscription options| Only one of our group members has the PC capabilities to run tests |
|Analysis Complexity (28) | 7 | 4 | The scope of the analysis may be very large for our time frame | Focus on AI and facial recognition and its handling specifically instead of all the research of Facebook's AI and data usage| Testing the algorithms will provide the implications we are searching for |
| Learning Curves (35) | 7 | 5 | Project team may need to acquire new skills for the project so there's a risk that productivity will be low | Try to keep the best member for a certain task doing what they understand best | No changes |
