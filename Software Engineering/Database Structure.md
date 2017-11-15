# Firebase Branch
### All patients ( Not using )

### apiKeys (Not using)

### cardSignUps 
> Contains all the card sign ups
- {Patient Mobile Number}  | {Patient UID} _string_

### cashSignUps
> Contains all the cash sign ups
- {Patient Mobile Number}  | {Patient UID} _string_

### checkedInPatients (Not using)
> Patients who checkedIn

### checkInMessages
> Sms templates which needs to be sent after a patient checks in.
- default - Default message for all the doctors. _string_
- {Doctor UID} | _string_

### dashboard (Not using)
> Contains all the stats and data about dashboard.

### deletedDoctorNotes (Not using)

### deletedPatientReports
> Reports which have been deleted.
- {Patient UID}
	- {File UID}
		- createdAt _double_
		- deletedAt _double_
		- description _string_
		- downloadUrl _string_ : Absolute download url for the file.
		- mimeType _string_
		- name _string_
		- storedAt _string_ : Relative path inside firebase storage

### doctorAdvice
> Doctor advice for each doctor
- {Doctor UID}
	- {Advice UID}
		- contentUrl _string_ : Absolute url for the html file.
		- priority _Int_ : Priority for the doctor advice. Can be used to sort in lists.
		- text _string_ : Placeholder text
		- title _string_ : Title of the advice
		- type _string_ (default, none)

### doctorAppointments
> Appointment numbers for doctors
- {Doctor UID} | {Mobile Number} _string_ : Appointment number for the respective doctor.

### doctorChats
> All the chats for a doctor
- {Doctor UID}
	- {Patient UID}
		- archived _boolean_
		- fullName _string_ : Patient Full Name
		- lastMessageCreatedAt _double_
		- lastMessageSentBy _string_ (doctor, patient)
		- lastMessageText _string_
		- lastMessageType _string_ (text, report, prescription)
		- lastViewedAt _long_

### doctorDashboard
> Dashboard stats for the doctor.
- details
	- {Doctor UID}
		- doctorCut _float_ : Fraction of the fees the doctor actually gets
		- receptionistIncentives
			- cashSignUpCut _float_ : Fraction of the fees receptionist gets by getting a cash sign up.
			- inIncentivePlan _boolean_
			- perCheckIn _Int_ : Amount earned per checkin
			- perDownload _Int_ : Amount earned per download
			- receptionistName _string_ 
			- receptionistPhoneNumber _string_
			- relationshipManager _string_ : Name of the RM from DocTalk.
- stats
	- {Doctor UID}
		- {Year}
			- {Timestamp for starting of the day}
				- amountPaidByPatients _Int_ : Total amount earned in the day.
				- numPatientsPaid: _Int_ : Total number of patients who paid on that day.
### doctorNotes
> Notes added by the doctor for each patient.
- {Doctor UID}
	- {Patient UID}
		- {Notes UID}
			- createdAt _double_
			- downloadUrl _string_ : Absolute url for the note file.
			- pageRank _Int_ : Used to order the notes.
			- storedAt _string_ : Relative path of the file inside storage.
		
### doctorPresence
> Is the doctor currently available on app
- {Doctor UID} | _boolean_ 

### doctorProfiles
> All the doctor profiles
- {Doctor UID} 
	- city _string_
	- emailAddress _string_
	- emergencyCallNumber _string_
	- fee _Int_
	- firstName _string_
	- lastName _string_
	- mobileNumber _string_
	- speciality _string_
	- subscriptionCode _string_

### doctorSavedResponses
> Saved responses for each doctor
- doctorSpecific
	- {Doctor UID}
		- {Saved Response UID} | _string_ : Saved response message

### doctorShareCodeMessages
> Share code messages for each doctor
- default _string_ : Default share code message.
- {Doctor UID} | _string_ : Customised share code message for the doctor.

### doctorSubscribers
> All the subscribers for the doctor
- {Doctor UID}
	- {Patient UID}
		- endsAt _double_
		- fee _Int_
		- fullName _string_
		- mobileNumber _string_
		- planType _string_ (full)
		- startedAt _double_
		- subscriptionId | {Subscription UID}

### doctorSubscriptionCodes
> Subscription codes for each doctor
- {Subscription Code} | {Doctor UID}

### emailAddresses
> All the email addresses registered with us.
- {Email Address} | [{Patient UID} , {Doctor UID}]

### employees
> All the DocTalk employees
- {Email Address}
	- accessLevel _Int_
	- admin _boolean_
	- fullName _string_
	- password _string_
	- username _string_

### foregroundStatus
> Current visibility of the doctor or patient on the respective app.
- [{Doctor UID}, {Patient UID}] | _boolean_


### inAppMessages
> Writing to this branch will display the message to the user in the app.  
- {Patient UID}
	- {In App Message UID}
		- action | string
		- body | string
		- buttonTitle | string
		- createdAt | double
		- title | string

### mandatoryUpdateBefore
> The version number stored in this branch is read by the client to compare against its own version and display a mandatory update message  
- [ios, android]
	- doctor
		- version _string_
	- patient
		- version _string_

### messages
> Messages between doctors and patients are stored here  
	- {DoctorUid|Patient UID}
		- {Message UID}
			- createdAt _double_
			- mimeType _string_
			- savedInFirebase _boolean_
			- sentBy _string_ [doctor, patient]
			- storedAt _string_ [{storageReferencePath}]
			- text _string_
			- type _string_ [text, report, prescription]

### mobileNumbers (LEGACY)

### notifications
> All notifications between users are stored here  
* {Notification UID}
	* actionType _string_ [DEFAULT,REPORT_CHAT,PRESCRIPTION_PATIENTS,OPEN_APP,REPORT]
	* message _string_
	* notificationSent _boolean_
	* receiverUid _string_ [{userUid}]
	* senderUid _string_ [{userUid}]
	* sentBy _string_ [patient, doctor]
	* versionCode _int_: to handle notifications for different android versions

### paidPatients (LEGACY)

### patientChats
> Patient chats shown in doctor cards in home screen are stored here  
* {Patient UID}
	* {Doctor UID}
		* fullName _string_: doctor full name
		* lastMessageCreatedAt _double_
		* lastMessageSentBy _string_ [doctor, patient]
		* lastMessageText _string_
		* lastMessageType _text_ [text, report, prescription]
		* lastViewedAt _double_

### patientFAQs
> Patient app wide faqs are stored here  
* {Faq UID}
	* question _string_
	* answer _string_

### patientPrescriptions
> Patient prescriptions are stored here  
* {Patient UID}
	* {Prescription UID}
		* createdAt _double_
		* description _string_
		* downloadUrl _string_
		* mimeType _string_
		* name _string_
		* origin _string_ [home, files, messages]
		* prescribedOn _double_
		* storedAt _string_ [{storagePath}]
		* uploadedBy _string_ [doctor, patient]

### patientProfiles
> Patient profiles are stored here  
* {Patient UID}
	* firstName _string_
	* lastName _string_
	* city _string_
	* emailAddress _string_
	* mobileNumber _string_
	* healthHistory _string_
	* allergies _string_
	* caseNumber _string_: LEGACY
	* age _int_: LEGACY
	* gender _string_ [{male, female}]
	* dob _double_

### patientReminders (LEGACY)

### patientReports
> Patient reports are stored here  
* {Patient UID}
	* {Prescription UID}
		* createdAt _double_
		* description _string_
		* downloadUrl _string_
		* mimeType _string_
		* name _string_
		* origin _string_ [home, files, messages]
		* testedOn _double_
		* storedAt _string_ [{storagePath}]
		* uploadedBy _string_ [doctor, patient]

### patientSubscriptions
> Patient subscription information is stored here  
* {Patient UID}
	* {Doctor UID}
		* endsAt _double_
		* fee _int_
		* fullName _string_: doctor full name
		* planType _string_ [full]
		* speciality _string_
		* startedAt _double_
		* subscriptionId _string_ [{Subscription UID}]

### payments (LEGACY)

### radiologistSignUps (LEGACY)

### receptionists (LEGACY)

### refreshTokens
> User device refresh tokens are stored here  
Android
* {Patient UID, Doctor UID}
	* {Device UID} _string_ [{token}]
iOS
* {Patient UID, Doctor UID}
	* {Device UID}
		* fcm _string_
		* os _string_ [ios]
		* token _string_

### reportSeen (LEGACY)

### scheduledMessages
> Writing here will schedule a message to be displayed in app  
* {Scheduled Message UID}
	* action _string_ [showPaymentScreen]
	* checkSubscription _boolean_
	* doctorUid _string_
	* messageText _string_
	* patientUid _string_
	* triggerAt _double_

### secondaryProfile
* {Patient UID}
	* {Secondary Profile UID}
		* allergies _string_
		* healthHistory _string_
		* dob _double_
		* name _string_
		* relationship _int_
		* sex _int_
		* pediatricPatientDataPoints
			* {dataPointUid}
				* BMI _double_
				* age _double_
				* headCirc _int_
				* height _int_
				* weight _int_

### specialityAdvice
> Speciality specific advice is stored here  
* {specialityName} [gynaecologist, paediatrician]
	* {Advice UID}
		* contentUrl _string_
		* priority _int_
		* text _string_
		* title _string_
		* type _string_ [default, doctorSpecific]

### specialityContent (LEGACY)

### staging (LEGACY)

### subscriptions (LEGACY)

### v2/mobileNumbers
> Mobile numbers of all mobile numbers are stored here (should be in sync with the auth table)  
* {mobileNumber}
	* uid _string_ [{Patient UID}]
	* signedUpOnPatientApp _boolean_

### v2/payments
> Information about payments made by patients  
* MODEL
	* amountPaid _int_
	* doctorUid _string_
	* method _string_ [cash, card]
	* name _string_: patient name
	* numberOfMonths _int_
	* paidOn _double_
	* patientUid _string_
	* status _string_ [captured, processed]
* doctorPatient
	* {Doctor UID}
		* {Patient UID}
			* {Payment UID}
				* MODEL
* patients
	* {Patient UID}
		* {Payment UID}
			* MODEL
* doctors
	* {Doctor UID}
		* {Payment UID}
			* MODEL
* master
	* {Payment UID}
		* MODEL

### v2/receptionists
> Receptionist details  
* {Receptionist UID}
	* associatedDoctors
		* {Doctor UID} _string_ [{doctorName}]
	* doctorUid _string_
	* fullname _string_
	* password _string_
	* receptionistUid _string_
	* username _string_

