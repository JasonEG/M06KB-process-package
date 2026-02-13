# Standard Operating Procedure



//SOP v1.5 JSON FORMAT

{
  "purpose": "Standardize the process for teachers to verify, weight, finalize, and store quarter or semester grades in PowerSchool, and to notify the secretary when grade storage is complete.",
  "scope": {
    "start_trigger": "Teacher receives an email from the building principal or secretary OR recognizes that the end of a quarter or semester is near.",
    "end_state": "All grades are stored in PowerSchool and an email confirmation has been sent to the secretary.",
    "in_scope": [
      "Logging into PowerSchool",
      "Verifying grade accuracy for all classes",
      "Adjusting traditional grade calculations",
      "Finalizing quarter or semester grades",
      "Email notification to the secretary"
    ],
    "out_of_scope": [
      "Entering individual assignments prior to verification",
      "System administration or configuration",
      "Post-finalization grade changes",
      "Communication with students or parents"
    ]
  },
  "roles": [
    {
      "role": "[ROLE: Teacher]",
      "responsibilities": [
        "Verify all grades are entered and accurate",
        "Apply correct grading weights",
        "Finalize grades",
        "Notify the secretary upon completion"
      ]
    },
    {
      "role": "[ROLE: Secretary]",
      "responsibilities": [
        "Receive confirmation email that grades are stored",
        "[TBD: Follow-up actions after notification]"
      ]
    },
    {
      "role": "[ROLE: Principal]",
      "responsibilities": [
        "Send reminder email indicating grading window"
      ]
    }
  ],
  "prerequisites": {
    "access": [
      "Valid username and password for PowerSchool"
    ],
    "tools": [
      "[SYSTEM_NAME] (PowerSchool / PowerTeacher Pro)"
    ],
    "required_information": [
      "List of assigned classes",
      "Awareness of current grading period (quarter or semester)"
    ]
  },
  "inputs": [
    "Existing grade data for all classes",
    "Selected grading period (quarter or semester)"
  ],
  "outputs": [
    "Finalized grades stored in PowerSchool",
    "Email confirmation sent to the secretary"
  ],
  "steps": [
    {
      "step_number": 1,
      "actor": "[ROLE: Teacher]",
      "action": "Determine that it is time to finalize grades by reviewing an email from the Principal or by recognizing that the end of the quarter or semester is approaching.",
      "decision": "Is it time to finalize grades?" "Yes: Proceed to Step 2." "No: End Process.",
      "evidence_ref": "Transcript: process start trigger",
      "notes": "No system action occurs in this step."
    },
    {
      "step_number": 2,
      "actor": "[ROLE: Teacher]",
      "action": "Log in to PowerSchool using a valid username and password.",
      "evidence_ref": "Transcript: login to PowerSchool",
      "notes": "This is a prerequisite. This step will fail if the prerequisite is not met."
    },
    {
      "step_number": 3,
      "actor": "[ROLE: Teacher]",
      "action": "Open PowerTeacher Pro by selecting it under a currently taught class.",
      "evidence_ref": "Transcript: click PowerTeacher Pro under class",
      "notes": ""
    },
    {
      "step_number": 4,
      "actor": "[ROLE: Teacher]",
      "action": "Navigate to Grading menu → Score Sheet option, use the class drop-down at the top of the screen to cycle through all classes, and verify that all quarter or semester grades are entered and accurate by reviewing each grade line by line.",
      "evidence_ref": "Transcript: grading and score sheet verification",
      "notes": "If grades are incorrect, they must be corrected before proceeding."
    },
    {
      "step_number": 5,
      "actor": "[ROLE: Teacher]",
      "action": "Open Settings menu → Traditional Grade Calculations option, select a class you currently teach, choose Actions menu → Edit option, and verify the grade weights for the quarter and semester.",
      "evidence_ref": "Transcript: traditional grade calculations",
      "notes": "Quarter exam set to 10%; remaining 90% allocated as percentages or total points."
    },
    {
      "step_number": 6,
      "actor": "[ROLE: Teacher]",
      "action": "Save the grade calculation changes for the class before exiting the Traditional Grade Calculations screen.",
      "evidence_ref": "Transcript: save before exiting each screen",
      "notes": "Must be repeated for all classes taught."
    },
    {
      "step_number": 7,
      "actor": "[ROLE: Teacher]",
      "action": "Navigate to Grading menu → Grades option → Traditional option to view the final quarter or semester grade for the selected class.",
      "decision": "Is the final grade correct?" "Yes: Proceed to Step 8." "No: Repeat Step 4.",
      "evidence_ref": "Transcript: traditional grades screen",
      "notes": ""
    },
    {
      "step_number": 8,
      "actor": "[ROLE: Teacher]",
      "action": "Move cursor to 'Final Grade Status' at the bottom of the screen and check “Semester or Quarter Final Grades Are Complete.”",
      "evidence_ref": "Transcript: final grade status pop-up",
      "notes": "Optional comment may be entered."
    },
    {
      "step_number": 9,
      "actor": "[ROLE: Teacher]",
      "action": "Move cursor to the grading-period drop-down at the top of the screen to repeat the finalization process for all classes taught.",
      "decision": "Are all classes finalized?" "Yes: Proceed to Step 10." "No: Repeat Step 7.",
      "evidence_ref": "Transcript: navigate through all classes",
      "notes": ""
    },
    {
      "step_number": 10,
      "actor": "[ROLE: Teacher]",
      "action": "Send an email to the Secretary confirming that all grades are stored in PowerSchool and then log out.",
      "evidence_ref": "Transcript: email notification to secretary",
      "notes": ""
    }
  ],
  "exceptions": [
    {
      "trigger": "Grades are missing or incorrect during verification.",
      "resolution_steps": [
        "Correct grades in the Score Sheet.",
        "Re-verify accuracy before continuing."
      ],
      "escalation": "Contact student if an assignment is missing. Otherwise mark a zero."
    },
    {
      "trigger": "Incorrect grading weights identified.",
      "resolution_steps": [
        "Reopen Traditional Grade Calculations.",
        "Adjust weights and save changes."
      ],
      "escalation": "Contact support personnel for assistance if you can't get it to work."
    },
    {
      "trigger": "Final Grade Status not marked complete for a class.",
      "resolution_steps": [
        "Return to Final Grade Status screen.",
        "Check completion box and save."
      ],
      "escalation": "If the program disallows you to mark complete check once again that you are in the correct grading period, THEN contact support."
    }
  ],
}

