# OVERALL #

$${\color{green}Summary}$$

- Session termination is crucial in the session lifecycle. To minimize the risk of session hijacking, the following security measures should be implemented:
  - Availability of User Interface Controls: Provide a clear and visible logout button on every page.
  - Session Timeout: Automatically terminate sessions after a defined period of inactivity.
  - Server-Side Session Invalidation: Ensure that the server-side session state is properly invalidated upon logout.
 
$${\color{green}Common \space issues \space include}$$

- Unclear Logout Functionality: Users may not trust or find the logout option if it’s ambiguous.
- Improper Session Termination: For example, changing the client-side session token without invalidating the server-side state.
- Lack of Server-Side Tracking: Some applications rely solely on cookies, which can be reused to access the session.
- Handling Browser or Tab Closure: Sessions should be automatically terminated after a period of inactivity.
- Single Sign-On (SSO) Systems: Ensure that logging out of one application does not leave active sessions in SSO systems or other connected applications.

$${\color{green}Test \space Objectives}$$

- Assess the usability and clarity of the logout UI.
- Analyze session timeout behavior and verify that the session is properly terminated after logout.

# HOW TO TEST #

$${\color{green}Testing \space the \space Log \space Out \space User \space Interface}$$\

- Check Visibility: Ensure a log out button is present on all pages and is easily identifiable.
- Position: The button should be visible without scrolling and ideally fixed in the browser viewport.

$${\color{green}Testing \space Server-Side \space Session \space Termination}$$

- Cookie Management: Store session cookies, then log out and observe changes. Attempt to access authenticated pages; if session cookies are reused, this indicates improper session termination.
- Page Security: No authenticated data should be visible post-logout. The application should redirect to a public area or login form.

$${\color{green} Testing \space Session \space Timeout}$$

- Timeout Detection: Determine session timeout by accessing pages with increasing delays. The delay before logout indicates the timeout value.
- Session Duration: Balance security and usability. For sensitive applications (e.g., banking), a shorter timeout (e.g., 1 minutes) is preferred, while less critical apps (e.g., forums) might allow longer timeouts

$${\color{green}Testing \space Single \space Sign-On \space (SSO) \space Environments}$$

- Log Out Verification: Perform log out in the application and SSO system. Ensure that logging out from SSO also terminates sessions in the connected application. Verify that authentication is required to re-access the application.
