
```js
export const systemModules = [
  {
    label: "Dashboard",
    route: "dashboard"
  },

  {
    label: "System Administration",
    links: [
      { label: "Account Management", route: "accounts" },
      { label: "Role Management", route: "roles" },
      { label: "Access Control", route: "permissions" },
      { label: "Security Policies", route: "security-policies" },
      { label: "System Updates", route: "system-updates" },
      { label: "User Guides", route: "user-guides" }
    ]
  },

  {
    label: "Documents & Regulations",
    links: [
      { label: "Organizational Policies", route: "organization-policies" },
      { label: "Workflow Processes", route: "workflow-processes" },
      { label: "Document Templates", route: "document-templates" }
    ]
  },

  {
    label: "Evaluation Framework",
    links: [
      { label: "Evaluation Criteria", route: "evaluation-framework" },
      { label: "Mandatory Activities", route: "mandatory-activities" }
    ]
  },

  {
    label: "Activity Planning",
    links: [
      {
        label: "Annual Planning",
        links: [
          { label: "Register Activity Plan", route: "activity-plan/register" },
          { label: "Approve Activity Plan", route: "activity-plan/approval" },
          { label: "Manage Activity Plans", route: "activity-plan/manage" }
        ]
      },
      {
        label: "Plan Deployment",
        links: [
          { label: "Send Notifications", route: "deployment/notifications" },
          { label: "Configure Registration Period", route: "deployment/registration-config" },
          { label: "Current Semester Activities", route: "deployment/current-semester" }
        ]
      }
    ]
  },

  {
    label: "Participation Tracking",
    links: [
      { label: "Record Participation", route: "participation/record" }
    ]
  },

  {
    label: "Participation Approval",
    links: [
      { label: "Approve Participation Records", route: "participation/approval" }
    ]
  },

  {
    label: "Complaint Management",
    links: [
      { label: "Handle Complaints", route: "complaints/handle" },
      { label: "Resolved Complaints", route: "complaints/resolved" }
    ]
  },

  {
    label: "Activity Monitoring",
    links: [
      { label: "Student Participation Monitoring", route: "monitor/student-participation" },
      { label: "Activity Implementation Monitoring", route: "monitor/activity-implementation" }
    ]
  },

  {
    label: "Academic Advisors",
    links: [
      { label: "Monitor Student Participation", route: "advisor/student-monitoring" },
      { label: "Monitor Student Activities", route: "advisor/activity-monitoring" }
    ]
  },

  {
    label: "Class Advisors",
    links: [
      { label: "Student Participation Monitoring", route: "class-advisor/student-monitoring" },
      { label: "Activity Monitoring", route: "class-advisor/activity-monitoring" }
    ]
  },

  {
    label: "Evaluation Councils",
    links: [
      { label: "Faculty Evaluation Council", route: "evaluation/faculty-council" },
      { label: "University Evaluation Council", route: "evaluation/university-council" }
    ]
  },

  {
    label: "Support Tools",
    links: [
      {
        label: "Academic Data Sync",
        links: [
          { label: "Academic Score Scale", route: "sync/academic-scale" },
          { label: "Score Conversion Rules", route: "sync/score-conversion" }
        ]
      },
      {
        label: "Attendance Tools",
        links: [
          { label: "Activity Attendance", route: "attendance/activity" }
        ]
      }
    ]
  },

  {
    label: "Evaluation Results",
    links: [
      { label: "Current Evaluation Results", route: "evaluation/current-results" },
      { label: "Evaluation History", route: "evaluation/history" }
    ]
  },

  {
    label: "Reports",
    links: [
      { label: "Faculty Reports", route: "reports/faculty" },
      { label: "University Reports", route: "reports/university" }
    ]
  },

  {
    label: "System Configuration",
    links: [
      { label: "Document Categories", route: "config/document-categories" },
      { label: "Email Configuration", route: "config/email" },
      { label: "Email Templates", route: "config/email-templates" },
      { label: "System Modules", route: "config/modules" },
      { label: "Academic Years & Semesters", route: "config/academic-years" },
      { label: "Code Generators", route: "config/code-generators" },
      { label: "Semester Student Lists", route: "config/semester-students" },
      { label: "Departments", route: "config/departments" },
      { label: "Activity Categories", route: "config/activity-categories" },
      { label: "System Settings", route: "config/system-settings" }
    ]
  }
];
```
