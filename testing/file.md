##1.	Document version history
Version	Comments	Author	Date

0.1	First draft	Andy M	19/11

0.2	Clarified change of AGM status to “Inactive” within new Alternative flow - discussed in internal review 	Andy M	01/12

0.3	Revised validation around planned attendees and AGM dates	Andy M	05/12

##2.	Brief Description
Allows relevant users to edit the upcoming AGM details for a GP. For new Managed GPs the Upcoming AGM is not active. This allows users to activate the upcoming AGM details, entering the meeting date and whether it is confirmed, the frequency and location, and planned attendees. They can update an active upcoming AGM to not active at any time and it will clear the previously saved AGM details.

##3.	Actor(s)
Investment Team User 

##4.	Trigger(s)
User selects to manage the upcoming AGM Details

##5.	Main Flow – Edit Upcoming AGM Details


1. User selects to edit the upcoming AGM details for this GP 
2. User enters the required upcoming AGM details 
	- Upcoming AGM fields
		- Frequency – mandatory; look-up: annual, bi-annual, quarterly, ad hoc
 		- Next AGM Date – mandatory; Date picker: DD-MMM-YY
			1.	RULE: The date of the AGM cannot be on or before the last meeting held.
				- Error message: “The date of the AGM is on or before the last meeting held. Please change to a valid date.”
			2.	RULE: AGM Date is normally future date, but can be changed to past date (less than today’s date). 
				- If AGM date is less than today, warn the user, and the AGM date must also be updated as a confirmed date (tick box) - this should be prompted if not already done
			3.	RULE: AGM Date is manually selected the first time an upcoming AGM is saved, and can be changed to a different date from then on (whether estimated or confirmed), but note one further restriction below on editing date: 
				- Once either the GP AGM Materials or an AGM Note has been uploaded for this AGM/ or this AGM’s AGM fund, the date can no longer be changed.
			4.	RULE: If the date selected is 7 days or less from today, the user is warned that the AGM documents will be emailed to the planned attendees on saving.
		- Next AGM Date confirmed? – tick box; un-ticked by default
			1.	Once date is confirmed, and the meeting date is in the past, the confirmation cannot be changed back to estimated.
			2.	Once date is confirmed, and the meeting date is in the past, the Funds Requiring an AGM Note are remembered for this AGM - so any subsequent changes of this indicator on the fund-level data will not change the fact that this fund requires an AGM Note for this past AGM
		-	Location – free text
		-	Planned Attendees – mandatory; 1 to many attendees; source from AD group AP DF InvestmentTeam
			1. On first editing, the Owner of the GP is defaulted, but can be changed
3.	User saves the details
4.	System checks, for an active AGM, that all mandatory information is complete 
	- NOTE: a meeting is active once the user saves some details and until the user marks the meeting as inactive, (see alternative flow).
5.	System redisplays an updated view of the managed GP details
6.	End Use Case

##6.	Alternative Flows
1. Update AGM status to “Inactive”
	- User selects to mark the upcoming AGM as Inactive
	- System asks the user to confirm the upcoming AGM will be marked inactive.
		- NOTE: If the meeting date is within next 7 days, highlight this fact – as part of the confirmation - to the user.
	- User confirms 
	- System removes the previously saved upcoming AGM details (meeting date, frequency, location, attendees)  and displays the AGM status as Inactive
	- End Use Case 

