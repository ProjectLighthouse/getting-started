### Release 1.4.3

🚀 __Added__
- Create UI to allow posts to have different owner and host
- Show all participating organizations logos on the opportunity cards

✍️ __Changed__
- Update the language and options on the Choose a Strategy screen when creating an opportunity
- Query by owner when getting posts for an organization
- Update the opportunity connect screen to include the host and owner if they are different
- Calculate unclaimed ranking boost for Algolia from owner instead of host
- Update the design and layout of the post cards
- Change background color of the app

🚑 __Fixed__
- Remove the edit post button from events in the past
- Send the correct segment event name when updating a registration


### Release 1.4.2

🚀 __Added__
- Add an admin menu to post cards the current user is authorized to update
- Add an admin toolbar to post pages the current user is authorized to update

✍️ __Changed__
- Query mongo rather than algolia when getting posts for admin screens
- Change query of posts for admins to return only posts the current organization owns rather than posts they host

🚑 __Fixed__
- Update packages to remove dependancies with malicious code
- Fix typos in SEO titles


### Release 1.4.1

🚑 __Fixed__
- Ensure primary contact is always included in registration segment events
- Fix error caused when registering as interested for an opportunity


### Release 1.4.0

✍️ __Changed__
- Use yarn in client Makefile instead of npm


### Release 1.3.9

🚀 __Added__
- Introduce Hot Module Replacement to the client
- Allow organization to post recurring events :tada:


✍️ __Changed__
- Restructured the client code, separating out the index into logical parts
- Asynchronous syncing of opportunity data to algolia
- The main feed will only show one opportunity per organization, if the organization has more than one opportunity a link to view all will be given
- Update the campaign reporting to rely on the new campaign model
- Remove shift array from algolia
- Move registration segment events from client to server


🚑 __Fixed__
- Organization stat numbers should be links
- Remove temporarily hard coded key in favor of hashicorp vault
- Ensure the complete organization profile alert is removed for all organization types
- Return user close to last scroll position after leaving and returning to the main feed


### Release 1.3.8

🚀 __Added__
- Show the campaign participants on the individual opportunity pages
- Display the location of an opportunity on the opportunity cards


✍️ __Changed__
- Update icons for sharing and interested, serving and following status
- Update language of serving and interested buttons
- Normalize color and style of action buttons for organizations and Opportunities
- Make currently registered shifts more clear on the registration select a shift screen


🚑 __Fixed__
- After updating an organization, the user is taken back to the organization page rather than the edit options screens
- Fix issue with apiUrl for reporting
- Prevent imgix var from being saved into the database for volunteer profile images


### Release 1.3.7

🚀 __Added__
- Add UI for creating and editing campaigns (Movements)
- Display participants of a campaign on opportunities associated to a campaign
- Create a 404 page


✍️ __Changed__
- Eject from Create-React-App
- Upgrade api to node 10.9.0
- Run client in Node rather than serving static files in production
- Use express middleware for Prerender
- Remove unused worker from the server directory
- Remove old env files
- Update the readme to be relevant to the current project
- Update campaigns so that the relevant information is stored on associated opportunities in Algolia
- Update names of segment events for organization partnership
- Fix map link for opportunities with shifts


🚑 __Fixed__
- Remove unnecessary call to get all organizations for the filter
- Fix insights endpoint to return upcoming or past registrations
- Fix breaking issue claim
- Fix issue when editing an opportunity with multiple shifts.


### Release 1.3.6

🚀 __Added__
- Add the ability to view and manage an organizations partners
- Track and store first and last touch attribution for users during sign up and registrations
- Add UI for downloading basic organization reports
- Add the logo of the organization currently in context to the navbar when viewing organization manage pages as an owner


✍️ __Changed__
- Change invite by email component from a modal to an on page component
- Merge promote screen with manage opportunity screen
- Update organization management routes
  - /:org-slug/manage/settings/basics
  - /:org-slug/manage/settings/other
  - /:org-slug/manage/insights
  - /:org-slug/manage/posts
  - /:org-slug/manage/posts/create
  - /:org-slug/manage/network
  - /:org-slug/manage/notifications
- Move select opportunity strategy into its own screens. Users can now select from:
  - Volunteer Interest
  - Host an Event
  - Join an Event
  - Repost
- Separate organization settings into two screens, Basics and Other
- Rename Opportunity to Post in the UI


🚑 __Fixed__
- Prevent error thrown when a user re-uses an already used claim code
- Add prerenderReady function so prerender does not cache the page to early


### Release 1.3.5

🚑 __Fixed__
- Move segment intercom settings to page track function


### Release 1.3.4

🚀 __Added__
- Index opportunities to algolia for main and organization feeds
  - Ranking is based on start date, registration spots available as a percent, the geolocation of the user based on IP address
- `Market` attribute added to organizations and is required
  - Can be set during on boarding and changed in admin
- Create API and data model for campaigns

✍️ __Changed__
- Integrate existing feed filters into algolia
- Shift location attributes now include latitude and longitude
- Shift location dropdown now uses algolia’s autocomplete component
- Hide intercom button on mobile devices until integration into ui

🚑 __Fixed__
- Remove unnecessary api call to get all organizations in filter component
- Prevent registrations of learn more cards from silently failing


### Release 1.3.3

🚑 __Fixed__
- Fix issue with primary contact email missing from segment registration events


### Release 1.3.2

🚑 __Fixed__
- Fix error in insights api when querying for sponsors
- Fix error created during merge


### Release 1.3.1

🚀 __Added__
- Create internal script to persist profile images from social authentication in AWS

🚑 __Fixed__
- Correctly recalculate registration counts when an opportunity is updated
- Fix the aggregation script to handle with missing records
- Fix the update organization function
- Fix the find by account to resolve aggregations
- Fix issue in aggregate script with document being saved multiple times in a single promise
- Fix typeError in account api
- Fix format=csv param in reporting script


### Release 1.2.9/1.3.0

🚑 __Fixed__
- Add/fix missing env var to production definitions


### Release 1.2.8

🚀 __Added__
- New endpoint for getting all the contacts for an organization
- Allow owners to set their organizations primary contact
- Allow the primary contact to be set for an opportunity and its shifts
- New insights endpoint for retrieving organization insights in either csv or json format
  - /api/insights/:organizationId/followers
  - /api/insights/:organizationId/members
  - /api/insights/:organizationId/registrations
  - /api/insights/:organizationId/registrations/:opportunitityId

✍️ __Changed__
- Deprecate siteManager on opportunities in favor of primaryContact
- Unless specified via props the Field component will prevent the browsers autocomplete
- Segment past and upcoming opportunities on the manage opportunities screen
- Include organization metadata in claim segment events
- Prevent shifts from being deleted when they already have registrations
- Downed verbosity level to 1 for less logs output
- Compatibility to ansible 2.5 and messenger deployment job
- Enhancements to opportunity create tools:
  - Minimum volunteers should not be required and default to 0
  - Add default dates and make the date component smarter when changing dates
  - Default opportunity status should be published
  - Clean up objects sent to api during create and update

🚑 __Fixed__
- Broken modal for deleting an organization was fixed
- Fix breaking tests
- Add a new field fullName to volunteers to be searched on, rather than first and last separately
- Fix type in segment registration event
- Add missing profile image to volunteers inside registration summary object
- Ignore placeholder Project Lighthouse account when evaluating the claim/unclaimed status of an organization


### Release 1.2.7

🚀 __Added__
- Stripe Lifecycle - Stripe will now communicate lifecycle events for manual subscriptions.
- Create theme for V1.0.0 of Material-Ui and begin migration process
- Support claiming of existing organizations. Claim methods:
  - Email domain
  - Manual review processes
- Add a Delete Organization button
- Add new virtual field to organizations called `unclaimed`
- Add new organization type `Community`

✍️ __Changed__
- search organizations endpoint now only queries on name, not descriptions.
- Name and email are auto-populated on the credit card screen.

🚑 __Fixed__
- Include new field to control the user current payment plan
- Change all uses and forms of Non-Profit to standardize on Nonprofit
- Ensure site_manager is always sent with segment registration event
- Ensure guests object on segment registration event is not an immutable map
- Fix infinite loop created when backing out of opportunity create screen
- Fix issue in which users were sent to the wrong url after changing their slug


### Release 1.2.6

🚀 __Added__
 - Plans & Billing - People can now choose a plan and subscribe to a recurring stripe plan with a CC during on-boarding.
 - Stripe Lifecycle - Stripe will now communicate lifecycle events like new invoices or failed payments to the API.

🚑 __Fixed__
 - Include missing opportunity `start_date` and `end_date` in segment registration event
 - Prevent shift title from overwriting opportunity title when creating a new opportunity
 - Fix Local issue with birth date when creating a new user


### Release 1.2.5

🚀 __Added__

- Partner cards are displayed in the feed for enabled organization categories
- Admins can now set the visibility of an opportunity to serve through the opportunity tools
  - Anywhere
  - Organization Page Only
  - Link Only

🚑 __Fixed__

- Correct broken endpoint `/api/organization/:organizationId/transfer/user/:userId` for transferring organizations


### Release 1.2.4

🚑 __Fixed__
- Fixed issue with segment event not including organization and opportunity fields for learn more requests


### Release 1.2.3

🚀 __Added__

- Org Partners - Organizations can now invite and accept partnership relationships via the API
- Org Partners - Organizations who have partners will see the partner logos and opportunities on their page.
- Org Partners/Promotion - Admins can now invite non-platform people to join lighthouse and create an organization.
- Org Promotion - Organizations can now select organizations to promote
- Org Promotion - Organizations who have promoted organizations will see opportunities from those organizations.
- Opportunities - Administrators can now make an opportunity private during create or edit.
- Opportunities - Opportunities now include `Host`, `Sponsor`, and `Owner` relationships and their opportunity cards will use the host and sponsor fields to present the logo / org name + with org name UI.

✍️ __Changed__

- UX - Organization admin menu's have been updated and simplified.
- UX - Only show the confirm edit cancel menus on screens where edits have been made but not saved.

🚑 __Fixed__

- Opportunities - Fixed issue where an opportunities primary contact was retuning null instead of inheriting the value from it's owning organization.


### Release 1.2.2

🚑 __Fixed__
 - Fix issue with mobile drawer appearing on desktop


### Release 1.2.1

🚀 __Added__
 - Add short list of organizations that a user owns or is an admin of to the mobile and desktop navigation
 - create page `/account/organizations` to view the organizations I am an owner or admin of
 - Return value `canManageOrganization` on an the logged in volunteer.
 - Add default images to new organizations based on the category they chose

✍️ Changed
 - Restructure desktop and mobile navigation
 - Update routes of pages for the authenticated user from the root to /account/:route. This includes:
   - `/account/notifications`
   - `/account/edit`
   - `/account/organizations`

🚑 __Fixed__
 - Fix copy link button on organization page
 - Correctly calculate if an opportunity or shift is past on the front end


### Release 1.2.0

🚀 __Added__
 - UI for onboarding to allow organizations to be created and managed
 - Wire up Stripe support to fascilitate payments in the future
 - Accounts now sit between users and organizations to fascilitate payments in the future
 - UI for opportunity creation
 - Volunteers can now join organizations, which allows for private opportunities to be created

✍️ __Changed__
 - Strip html from various fields which might allow for XSS

🚑 __Fixed__
 - Updating an opportunity did not correctly update its shifts


### Release 0.2.0 (hotfix)

🚑 __Fixed__
 - [Fixed bug](https://github.com/ProjectLighthouse/lighthouse/commit/1c485ac7f2980895a6de62006858378f6509e0cf) which tried to reference a shift which was deleted directly from the database.

### Release 0.1.9

🚀 __Added__
 - Opportunities without a shift will be visible with a "Learn More" button instead of being able to register for opportunity.
 - A volunteer can now request to join an organization; and organization can handle requests (API only).
 - Markdown editor can be used to edit opportunities.

✍️ __Changed__
 - Opportunities can be created without a shift.

🚑 __Fixed__
 - New volunteers, who register through facebook and google, will have their profile images cached for future use


### Release 0.1.8

🚀 __Added__
 - Opportunities can now be created.
 - Opportunities can now be edited and drafts can be saved for later edits.
 - Password can now be reset.

✍️ __Changed__
 - Some Opportunity Registrations require agreements to be signed.

🚑 __Fixed__
 - Prevent removing a shift that has registrations associated with it.
 - Updating an organization will default to the pre-existing organization type (was being reset if not explicitly sent).


### Release 0.1.7

Release 0.1.7 was skipped due to a hotfix from 0.1.6


### Release 0.1.6

✍️ __Changed__
 - Organizations now include a list of admins and the owner on every API call from a logged-in volunteer.
 - You can now change ownership of an organization by calling the `POST /organization/:organization` endpoint and including the `owner` field, pointing to the volunteer you would like to pass ownership to.
 - Return summary of volunteers serving and volunteers interested from the API.

🚑 __Fixed__
 - Registration processes was not accepting "additional" guests. Hotfix was created to fix. Affected users have been contacted.
 - Fix location lists for organizations.
