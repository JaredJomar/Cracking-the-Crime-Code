# Cracking-the-Crime-Code

## Part 1: Cracking the Crime Code 

### Objective
The objective of Part 1 of the project is to assist the Police Department's IT team in deciphering hidden messages within flyers used by criminal organizations for communication. The project aims to extract critical information, such as the identity of the operation's leader and the organization responsible for the message. Additionally, the project involves designing a strategy to make the most arrests possible based on the deciphered information and generating a detailed report on the arrests made.

### Project Details
#### Part 1: Deciphering the Messages
In this phase, the goal is to extract specific information from seemingly innocent flyers. The key details to extract are:
- **Organization Identification**: Criminal organizations identify themselves with numbers 1 through 9, determined by calculating the digital root of the serial number found on the flyer.
- **Leader Identification**: The leader's identity is found by reading the first character of the `ith` word in each line of the flyer's content.

#### Part 2: Arrest Operation
Once the leader of the criminal operation is identified, the project moves to the arrest phase. The process involves the following steps:
1. Arrest the leader.
2. Arrest all their underlings.
3. Identify which underling has the most underlings under their supervision.
4. Continue arresting underlings recursively until the lowest-ranking member is reached. This process aims to maximize the number of arrests made within the organization.

#### Part 3: Report
After processing all the messages included in the case, a comprehensive report is generated. The report includes:
- Name of the captain in charge.
- Total arrests made.
- The status of all available criminal organizations, including the hierarchy within each organization.

## Part 2: Additional Project Details

### ArrestOperation Class
The `ArrestOperation` class serves as the main driver for the project, using a `PoliceDepartment` object to perform all the necessary steps outlined in Part 1 - 3 of the project specifications. The class consists of a `main()` method, and additional private methods can be added as needed.

In the `main()` method, the following tasks are accomplished:
- Determine the current case's input file path (caseFolder).
- Create a `PoliceDepartment` object with Captain Morgan as the captain.
- Utilize the `PoliceDepartment` object to:
  1. Set up the Organization List for the PoliceDepartment.
  2. Iterate through the files in the `Flyer` folder, deciphering the organization and leader, and making arrests as necessary.
  3. Generate a report summarizing the arrests.

### Member Class
The `Member` class represents members of criminal organizations and holds the following information:
- Name of the member.
- Nickname of the person within the organization (primary identifier).
- List of underlings (members supervised by this person).
- The member's rank within the organization.
- The nickname of the member that supervises them.
- Whether this member is arrested (initially set to false).

### Organization Class
The `Organization` class represents a criminal organization and contains the following information:
- Name of the organization.
- Boss of the organization (a `Member` object).
- Key for deciphering the leader.

Some methods of importance within the `Organization` class include:
- `setupOrganization()`: This method sets up the organization by reading a file with organization information.
- `organizationTraversal()`: This method traverses the organization hierarchy and returns a sub-list of members that comply with a given lambda function, acting as a filter.
