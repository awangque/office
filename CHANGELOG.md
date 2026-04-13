# Changelog 

![stage](https://img.shields.io/badge/Idea%20|%20Prototype-0.0.x-red) ![stage](https://img.shields.io/badge/Working%20(Incomplete)-0.x.0-yellow) ![stage](https://img.shields.io/badge/Stable-x.0.0-green)

#### 🚧 A solo-built project developed in my spare time, emphasizing gradual progress, continuous learning, and thoughtful iteration over speed.

---

### Dec 2025 
![stage](https://img.shields.io/badge/Stage-Prototype-red) ![version](https://img.shields.io/badge/Version-0.0.1-blue)

#### Added 
- Create 2-level authentication.
- Built 3 pages with basic simple layout (AccessCode, Login, Dashboard), total of 5 pages for 2 companies.

#### Results & Comment
```
https://script.google.com/macros/s/AKfycbw4XxoG4PIKYvRC0SKy4BdpdZYviP7XHYMfgY7n6mV2OiKf2sRWNhqBkmPNjqk0cpHr/exec
```

```
Access Code : ABC123 (company A) / XYZ789 (company B)

Company A
Username: admin | Password: admin123 /// Username: staff | Password: staff123

Company B
Username: admin | Password: adminB /// Username: staff1 | Password: staffB 
```
- I treated all the pages as a traditional multi-page application (MPA).
- Ref: AC1.26

#### So what's next ?
- Smoothen the system flow.

---

### Jan 2026
![stage](https://img.shields.io/badge/Stage-Prototype-red) ![version](https://img.shields.io/badge/Version-0.0.2-blue) 
#### Added
- Logout function were introduced inside the dashboard page.
- Module were added so admin and staff will have different dashboard view.

#### Changes
- Initially we have 1 universal AccessCode page, and now we also made 1 universal Login page too (refactored).
- Dashboard load different module content between admin and staff.
  
#### Results & Comment
```
https://script.google.com/macros/s/AKfycbyhlWivSUzh9swfkxXuJRgOIQkMnk-hlKgMhzPEw_NRu84ljBH6RHn87t734-weimg/exec
```
```
Access Code : ABC123 (company A) / XYZ789 (company B)

Company A
Username: admin | Password: admin123 /// Username: staff | Password: staff123

Company B
Username: admin | Password: adminB /// Username: staff1 | Password: staffB 
```
- Navigation flow from AccessCode > Login > Dashboard > AccessCode (on logout) works as intended.
- Multi dashboard layout is also allowed if needed, not everyone like similar dashboard UI.
- Ref: AC1.64

#### So what's next ?
- The risk of current idea, if I have 5 companies or more, I will have repetitive set of dashboard pages.
- UI is minimal for now, focus has been on completing the functional flow. May proceed with UI-UX next.

---

### Feb 2026
![stage](https://img.shields.io/badge/Stage-Prototype-red) ![version](https://img.shields.io/badge/Version-0.3.0-blue) 
#### Added
- New UI for all pages (AccessCode, Login and Dashboard)
- Security measurement implemented.
#### Changes
- Dashboard page were refactored to be universal use. (every user will have the same UI).
- Remove all add module ideas, less hassle, keep it simple.
- Remove all debug function, so it won't expose internal in production.
```
/* =====================================================
   DEBUG PURPOSES
===================================================== */
function debugToken(token) {
  return PropertiesService.getScriptProperties().getProperty(token);
}

function debugProperties() {
  return PropertiesService.getScriptProperties().getProperties();
}

function clearAllSessions() {
  PropertiesService.getScriptProperties().deleteAllProperties();
}

function resetAll() {
  PropertiesService.getScriptProperties().deleteAllProperties();
}

function inspectToken(token) {
  const all = PropertiesService.getScriptProperties().getProperties();
  return {
    lookingFor: "SESSION_" + token,
    exists: !!all["SESSION_" + token],
    allKeys: Object.keys(all)
  };
}
```

#### Results & Comment
```
https://script.google.com/macros/s/AKfycbzi8vr_Rll2LUM9rcTLz4gpz4CZ4ER_HSRguEqzib0tYI-sBe54yF9E5kGBZF6UGd-p/exec
```
```
Access Code : viewpoint01 (company A) / vyral02 (company B)

Company A
Username: admin | Password: admin123 /// Username: staff | Password: staff123

Company B
Username: admin | Password: adminB /// Username: staff1 | Password: staffB 
```
- Adding more companies become easier and inviting now.
- Found how-to hide the google notification using iframe.
- Implementing the UI properly was very challenging due to rendering timing issues since this is under Google environment.
- Found out that the Google ecosystem only stable up to 50,000 rows of data and limited only with 200 versions of webapp.
- Found out that Google has 6-mins per request of execution time and daily quotas (read/write).
- Ref: AC1.100.180

#### So what's next ?
The current 3-page MPA setup effectively manages Google’s execution constraints, but load times will likely increase with scale. To maintain high performance and responsiveness, I plan to transition the project to an SPA architecture.

---
### Mar 2026
![stage](https://img.shields.io/badge/Stage-Working%20(Incomplete)-yellow) ![version](https://img.shields.io/badge/Version-0.5.0-blue) 
#### Added
- Use temporary dummy data (hard-coded).
#### Changes
- Dashboard UI were updated again.
- Hybrid SPA architecture implemented.
- Both Manager and Staff dashboard were removed (temporarily).
#### Results & Comment
```
https://script.google.com/macros/s/AKfycbxvDKDdZJpJcPNmxAxCM6y7IVsaxOVVzO9akvIexH4747SlerFVCaKzXZwfQscZKzYRmQ/exec
```
```
Access Code : viewpoint01 (company A) / vyral02 (company B)

Company A
Username: admin | Password: admin123 

Company B
Username: admin | Password: adminB  
```
- Encounter countless blank page errors while transitioning to SPA compared to plug-and-play MPA architecture.
- The use of ID classes is important for SPA to work.
- The security system is now become a Session-Based Authentication.
- All references from youtube were actually limited to only single company/personal use, not multi-tenant (and majority uses Bootstrap framework). Found 1 real use with this Google ecosystem that intented to work for company system planning, dated 25/3/26.
```
https://drive.google.com/file/d/1P4D57yFQG43TroYo79jkM2vJrFpD9MIA/view
```
- [Hybrid SPA](ANALYTICS.md) architecture were chosen base on risk and complexity matters.
- Ref: Version 94

#### So what's next ?
- Create receipt and invoice template, for Settings sidebar menu.
- Optimizing the current hybrid SPA.
  
---
### Apr 2026
![stage](https://img.shields.io/badge/Stage-Working%20(Incomplete)-yellow) ![version](https://img.shields.io/badge/Version-0.6.0-blue) 
#### Added
- Business sections updated (BizInfo & document template)

#### Changes
- Optimization of hybrid SPA (version 2).

#### Results & Comment
- Not sure yet

#### So what's next ?
- Depends to what kind of priority problem occurs.

---
### May 2026
