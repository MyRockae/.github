# Rockae Portal - Comprehensive Testing Guide

This document provides a complete testing guide for all pages in the Rockae Portal application. Testers should verify both visual appearance and functionality on both mobile and web browsers.

**Base URL**: `http://beta-test.rockae.com` (or current testing environment URL)

---

## Table of Contents

1. [Authentication Pages](#authentication-pages)
2. [Main User Pages](#main-user-pages)
3. [Community Pages](#community-pages)
4. [Blog Pages](#blog-pages)
5. [Admin Pages](#admin-pages)
6. [General Testing Notes](#general-testing-notes)

---

## Authentication Pages

### 1. Home/Landing Page
**URL**: `http://beta-test.rockae.com/`

**Visual Checks:**
- [ ] Page loads correctly on both mobile and desktop
- [ ] Logo is visible and properly positioned
- [ ] Navigation menu is responsive (hamburger menu on mobile)
- [ ] Hero section is visible with proper spacing
- [ ] Footer is displayed correctly
- [ ] All images and graphics load without errors

**Functionality Tests:**
- [ ] Clicking "Sign In" button redirects to `/login`
- [ ] Clicking "Sign Up" or "Register" button redirects to `/register`
- [ ] If user is already logged in, should redirect to `/wall`
- [ ] All links in navigation and footer work correctly
- [ ] Page scrolls smoothly on both devices

---

### 2. Sign Up Page
**URL**: `http://beta-test.rockae.com/register`

**Visual Checks:**
- [ ] Form is centered and well-aligned on desktop
- [ ] Form is properly sized on mobile (not cut off, scrollable)
- [ ] Input fields are clearly visible with proper labels
- [ ] Logo is visible at the top
- [ ] Password field shows/hides toggle icon is visible
- [ ] Error messages display with proper styling (red text)
- [ ] Success messages display correctly

**Functionality Tests:**
- [ ] Enter first name - field accepts input
- [ ] Enter last name - field accepts input
- [ ] Enter email address - validates email format
- [ ] Enter password - shows/hides password when toggle is clicked
- [ ] Password strength indicator works (if present)
- [ ] Check "I agree to terms and conditions" checkbox
- [ ] Submit form with valid data
- [ ] Verify redirect to verification/resend page or success message
- [ ] **Check email inbox for verification email** - email should arrive within 1-2 minutes
- [ ] Verify email contains verification link
- [ ] Try submitting with empty fields - should show validation errors
- [ ] Try submitting with invalid email format - should show error
- [ ] Try submitting with weak password - should show error (if validation exists)
- [ ] Click "Sign In" link - should redirect to login page
- [ ] If already logged in, should redirect away from this page

---

### 3. Sign In / Login Page
**URL**: `http://beta-test.rockae.com/login`

**Visual Checks:**
- [ ] Form is properly centered on desktop
- [ ] Form is responsive on mobile
- [ ] Logo is visible
- [ ] Email and password fields are clearly labeled
- [ ] Password show/hide toggle is visible
- [ ] "Forgot password?" link is visible
- [ ] "Create an Account" button is visible
- [ ] Error messages display correctly

**Functionality Tests:**
- [ ] Enter valid email address
- [ ] Enter password
- [ ] Toggle password visibility (eye icon)
- [ ] Submit with valid credentials - should log in successfully
- [ ] After successful login, should redirect to `/my-account` or `/wall`
- [ ] Try logging in with invalid email - should show error message
- [ ] Try logging in with wrong password - should show error message
- [ ] Try logging in with empty fields - should show validation errors
- [ ] Click "Forgot your password?" link - should redirect to `/forgot-password`
- [ ] Click "Create an Account" button - should redirect to `/register`
- [ ] If already logged in, should redirect away from login page
- [ ] Check that user session persists after page refresh

---

### 4. Email Verification Success Page
**URL**: `http://beta-test.rockae.com/register/verification/:verificationToken`

**Visual Checks:**
- [ ] Success message is displayed clearly
- [ ] Page is responsive on mobile and desktop
- [ ] Appropriate success icon/indicator is visible

**Functionality Tests:**
- [ ] Click verification link from email - should open this page
- [ ] Verify success message appears
- [ ] Check that user can proceed to login
- [ ] Try using an invalid or expired token - should show error message
- [ ] Try using the same token twice - should handle appropriately

---

### 5. Resend Verification Email Page
**URL**: `http://beta-test.rockae.com/register/resend-verification`

**Visual Checks:**
- [ ] Form is properly displayed
- [ ] Instructions are clear and visible
- [ ] Responsive on all devices

**Functionality Tests:**
- [ ] Enter email address
- [ ] Click "Resend Verification Email" button
- [ ] Verify success message appears
- [ ] Check email inbox for new verification email
- [ ] Try with invalid email format - should show error
- [ ] Try with non-existent email - should handle gracefully

---

### 6. Forgot Password Page
**URL**: `http://beta-test.rockae.com/forgot-password`

**Visual Checks:**
- [ ] Form is centered and well-presented
- [ ] Logo is visible
- [ ] Instructions are clear
- [ ] Responsive on mobile and desktop

**Functionality Tests:**
- [ ] Enter registered email address
- [ ] Click "Send Reset Link" button
- [ ] Verify success toast/message appears
- [ ] **Check email inbox for password reset email** - should arrive within 1-2 minutes
- [ ] Verify email contains reset password link
- [ ] Try with invalid email format - should show error
- [ ] Try with non-existent email - should handle appropriately (don't reveal if email exists)
- [ ] Click "Back to Login" link - should redirect to `/login`

---

### 7. Reset Password Page
**URL**: `http://beta-test.rockae.com/reset-password/:resetPasswordToken`

**Visual Checks:**
- [ ] Form displays correctly
- [ ] Password and confirm password fields are visible
- [ ] Show/hide password toggles work
- [ ] Responsive on all devices

**Functionality Tests:**
- [ ] Click reset link from email - should open this page
- [ ] Enter new password
- [ ] Enter confirm password
- [ ] Toggle password visibility for both fields
- [ ] Submit with matching passwords - should reset successfully
- [ ] Try with mismatched passwords - should show error
- [ ] Try with weak password - should validate (if validation exists)
- [ ] Try with invalid/expired token - should show error message
- [ ] After successful reset, should redirect to login page
- [ ] Verify old password no longer works
- [ ] Verify new password works for login

---

## Main User Pages

### 8. General Wall Page
**URL**: `http://beta-test.rockae.com/wall`

**Visual Checks:**
- [ ] Navigation bar is visible and properly styled
- [ ] Left sidebar shows profile information (on desktop)
- [ ] Left sidebar shows "My Communities" frame
- [ ] Right sidebar shows "Communities by Interest" and "Trending Communities" (on desktop)
- [ ] Main content area displays posts/feed
- [ ] Post creation input field is visible at top
- [ ] Page is responsive - sidebars stack on mobile
- [ ] Footer is visible

**Functionality Tests:**
- [ ] Click on post creation field - should open modal
- [ ] Create a new post with text
- [ ] Create a post with image attachment
- [ ] Create a post with multiple images
- [ ] Submit post - verify it appears in feed
- [ ] Click on a community card - should navigate to that community
- [ ] Click on "My Communities" items - should navigate correctly
- [ ] Click on trending/interest communities - should navigate correctly
- [ ] Scroll through posts - infinite scroll works (if implemented)
- [ ] Like/unlike posts
- [ ] Comment on posts (if enabled)
- [ ] Share post (if button exists)
- [ ] Click on user profile/avatar - should navigate to profile
- [ ] Navigation links work correctly
- [ ] Logout button works (if present)

---

### 9. My Account Profile Page
**URL**: `http://beta-test.rockae.com/my-account`

**Visual Checks:**
- [ ] Profile banner/header displays correctly
- [ ] Profile avatar is visible
- [ ] User name is displayed correctly
- [ ] Statistics cards show (communities owned, joined, posts)
- [ ] "About" section is visible
- [ ] "Interests" section displays correctly
- [ ] "My Communities" list is visible
- [ ] "Communities Owned" list is visible (if user owns communities)
- [ ] "Trending Communities" and "Communities by Interest" sections visible
- [ ] Edit profile button/icon is visible
- [ ] All sections are responsive on mobile

**Functionality Tests:**
- [ ] Click "Edit Profile" - should open edit modal or navigate to settings
- [ ] Click on a community in "My Communities" - should navigate to that community
- [ ] Click on a community in "Communities Owned" - should navigate correctly
- [ ] Click on trending/interest communities - should navigate correctly
- [ ] View analytics (if "Show Analytics" button exists)
- [ ] Statistics numbers are accurate
- [ ] All links and buttons are clickable
- [ ] Profile information loads correctly
- [ ] Page scrolls smoothly

---

### 10. Account Settings Page
**URL**: `http://beta-test.rockae.com/my-account/settings`

**Visual Checks:**
- [ ] Settings form/sections are visible
- [ ] All form fields are properly labeled
- [ ] Save buttons are visible
- [ ] Page is responsive on mobile and desktop

**Functionality Tests:**
- [ ] Update personal information (name, bio, etc.)
- [ ] Save changes - verify success message
- [ ] Update email address (if allowed)
- [ ] Change password
- [ ] Update profile picture/avatar
- [ ] Update interests/tags
- [ ] Verify changes persist after page refresh
- [ ] Test form validation
- [ ] Cancel button works (if present)

---

### 11. Find Community / Community Finder Page
**URL**: `http://beta-test.rockae.com/find-community`

**Visual Checks:**
- [ ] Search bar is visible at the top
- [ ] Filter options are visible (if present)
- [ ] Community cards are displayed in grid layout
- [ ] Each card shows community name, avatar, description
- [ ] Grid shows 3-4 cards per row on desktop
- [ ] Cards stack vertically on mobile
- [ ] Page spacing and gaps are consistent

**Functionality Tests:**
- [ ] Search for communities by name
- [ ] Filter by category (if filters exist)
- [ ] Click on a community card - should navigate to community preview
- [ ] Scroll through community list
- [ ] Pagination works (if present)
- [ ] Empty state displays when no results found
- [ ] Loading state displays during search

---

### 12. Create Community Page
**URL**: `http://beta-test.rockae.com/create-community`

**Visual Checks:**
- [ ] Form is well-organized and visible
- [ ] All required fields are marked
- [ ] File upload areas are visible
- [ ] Form is responsive on mobile

**Functionality Tests:**
- [ ] Enter community name
- [ ] Enter community alias/slug
- [ ] Enter description
- [ ] Upload community banner image
- [ ] Upload community avatar/logo
- [ ] Select category (if dropdown exists)
- [ ] Set community type (public/private/paid)
- [ ] Configure privacy settings
- [ ] Set pricing (if paid community)
- [ ] Submit form - verify community is created
- [ ] Verify redirect to new community page
- [ ] Test form validation (empty fields, invalid formats)
- [ ] Cancel button works (if present)

---

## Community Pages

### 13. Community Preview Page (Public)
**URL**: `http://beta-test.rockae.com/community/:alias`

**Visual Checks:**
- [ ] Community banner is displayed
- [ ] Community avatar/logo is visible
- [ ] Community name and description are shown
- [ ] "Join Community" button is visible (if not a member)
- [ ] Home content section displays featured content
- [ ] Summary card shows member count, pricing, etc.
- [ ] Description section is visible
- [ ] Tags/interests are displayed
- [ ] Similar communities section is visible
- [ ] Page is responsive on all devices

**Functionality Tests:**
- [ ] Click "Join Community" - should show join flow or redirect to login
- [ ] Click on featured content items - should display in larger view
- [ ] Click on similar communities - should navigate to those communities
- [ ] Scroll through page - all sections load correctly
- [ ] If already a member, "Access Community" button should be visible
- [ ] Pricing information displays correctly (if paid community)
- [ ] Member count is accurate

---

### 14. Community Home Page (Member View)
**URL**: `http://beta-test.rockae.com/community/:alias/home`

**Visual Checks:**
- [ ] Community navigation bar is visible
- [ ] Top section shows featured content/media
- [ ] Summary card displays on right (desktop) or below (mobile)
- [ ] Description section with tags is visible
- [ ] "Your Membership" card is visible
- [ ] "Community Info" card is visible
- [ ] Public notes section is visible
- [ ] All sections are responsive

**Functionality Tests:**
- [ ] Click on featured content - should display in larger view
- [ ] Click on tags/interests - should filter or navigate (if functional)
- [ ] Navigate between tabs (Home, Town Hall, Walls, etc.)
- [ ] Membership information is accurate
- [ ] Click on "Community Info" - verify details display
- [ ] Scroll through page - all content loads

---

### 15. Community Town Hall Section
**URL**: `http://beta-test.rockae.com/community/:alias/town-hall`

**Visual Checks:**
- [ ] Post creation area is visible
- [ ] Posts are displayed in chronological order
- [ ] Each post shows author, timestamp, content
- [ ] Reply buttons are visible
- [ ] Like/reaction buttons are visible
- [ ] Share button is visible (if present)
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Click post creation field - should open modal
- [ ] Create a new post with text
- [ ] Create a post with image(s)
- [ ] Create a post with video
- [ ] Submit post - verify it appears in feed
- [ ] Click "Reply" on a post - should open reply form
- [ ] Submit reply - verify it appears nested under post
- [ ] Like/unlike posts
- [ ] Share post - verify shareable URL works
- [ ] Delete own posts (if allowed)
- [ ] Edit own posts (if allowed)
- [ ] Scroll through posts - pagination works
- [ ] Click on author name - should navigate to profile
- [ ] Deep linking works: `/town-hall?postId=123` - should scroll to and highlight post

---

### 16. Community Walls / Forums Section
**URL**: `http://beta-test.rockae.com/community/:alias/walls`

**Visual Checks:**
- [ ] Left sidebar shows list of walls/forums (on desktop)
- [ ] Mobile hamburger menu button is visible (on mobile)
- [ ] Selected wall's posts are displayed in main area
- [ ] Post creation area is visible
- [ ] Posts display with replies nested
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Click on different walls in sidebar - should load that wall's posts
- [ ] On mobile, click hamburger menu - sidebar should slide in
- [ ] Create a new post in selected wall
- [ ] Reply to posts
- [ ] Reply to replies (nested replies)
- [ ] Like/unlike posts
- [ ] Share post - verify URL includes wallId and postId
- [ ] Deep linking works: `/walls?wallId=123&postId=456` - should select wall and scroll to post
- [ ] Edit/delete own posts (if allowed)
- [ ] Posts are filtered by selected wall
- [ ] Empty state shows when wall has no posts

---

### 17. Community Classrooms Section
**URL**: `http://beta-test.rockae.com/community/:alias/classrooms`

**Visual Checks:**
- [ ] List view shows classroom cards in grid
- [ ] Each card shows classroom banner, title, description
- [ ] "Create Classroom" button is visible (for owners/moderators)
- [ ] Grid layout is responsive (fewer columns on mobile)
- [ ] Detail view shows sidebar with classroom items (on desktop)
- [ ] Mobile hamburger menu button is visible (on mobile)

**Functionality Tests:**
- [ ] Click "Create Classroom" - should open creation modal
- [ ] Create classroom with banner, title, description
- [ ] Click on a classroom card - should open classroom detail view
- [ ] In detail view, sidebar shows list of content items
- [ ] Click on content item - should display in main content area
- [ ] Click "Add Content" - should open content creation modal
- [ ] Create content with file upload
- [ ] Create content with URL
- [ ] Edit content (pen icon in content view)
- [ ] Delete content
- [ ] Drag and drop to reorder content items (owners/moderators only)
- [ ] Deep linking works: `/classrooms?classroomId=123` - should open classroom
- [ ] Deep linking works: `/classrooms?classroomId=123&contentId=456` - should open classroom and content
- [ ] On mobile, hamburger menu opens sidebar
- [ ] Mobile sidebar only scrolls content list, not entire sidebar
- [ ] Share classroom URL - should work when opened
- [ ] Share content URL - should work when opened

---

### 18. Community Calendars Section
**URL**: `http://beta-test.rockae.com/community/:alias/calendars`

**Visual Checks:**
- [ ] Calendar view is displayed
- [ ] Navigation between months/weeks works
- [ ] Events are visible on calendar
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Create new event
- [ ] Click on existing event - should show details
- [ ] Edit event
- [ ] Delete event
- [ ] Navigate between months
- [ ] Filter events (if filters exist)

---

### 19. Community Members Section
**URL**: `http://beta-test.rockae.com/community/:alias/members`

**Visual Checks:**
- [ ] Member list is displayed
- [ ] Each member shows avatar, name, role
- [ ] Search/filter options are visible (if present)
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Search for members by name
- [ ] Filter by role (owner, moderator, member, etc.)
- [ ] Click on member - should navigate to profile
- [ ] For owners/moderators: assign roles, remove members
- [ ] Member count is accurate

---

### 20. Community Messages Section
**URL**: `http://beta-test.rockae.com/community/:alias/messages`

**Visual Checks:**
- [ ] Conversation list is visible
- [ ] Message thread displays selected conversation
- [ ] Message input field is visible
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Click on conversation - should load messages
- [ ] Send a message
- [ ] Send message with attachment
- [ ] Messages appear in real-time (if real-time enabled)
- [ ] Deep linking works: `/messages?conversationId=123` - should open conversation
- [ ] Create new conversation

---

### 21. Community Member Settings Section
**URL**: `http://beta-test.rockae.com/community/:alias/member-settings`

**Visual Checks:**
- [ ] Settings form is visible
- [ ] All options are clearly labeled
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Update notification preferences
- [ ] Leave community option works
- [ ] Save settings - verify changes persist

---

### 22. Community Settings Page (Owner/Admin)
**URL**: `http://beta-test.rockae.com/community/:alias/settings`

**Visual Checks:**
- [ ] Settings form is visible
- [ ] All tabs/sections are accessible
- [ ] Save buttons are visible

**Functionality Tests:**
- [ ] Update community name, description
- [ ] Upload new banner/avatar
- [ ] Update community category
- [ ] Change privacy settings
- [ ] Update pricing (if paid community)
- [ ] Manage payment plans
- [ ] Manage classrooms, walls, calendars
- [ ] Save all changes - verify they persist
- [ ] Delete community (if option exists)

---

## Blog Pages

### 23. Blog Search/Browse Page
**URL**: `http://beta-test.rockae.com/blogs`

**Visual Checks:**
- [ ] Blog post cards are displayed in grid
- [ ] Each card shows featured image, title, excerpt
- [ ] Search bar is visible
- [ ] Filter options are visible (if present)
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Search for blog posts
- [ ] Filter by category/tag
- [ ] Click on blog post card - should navigate to full post
- [ ] Pagination works
- [ ] Sorting options work (if present)

---

### 24. View Blog Post Page
**URL**: `http://beta-test.rockae.com/blog/:slug`

**Visual Checks:**
- [ ] Full blog post is displayed
- [ ] Featured image is visible
- [ ] Title and author information is shown
- [ ] Content is well-formatted
- [ ] Related posts section is visible (if present)
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Read full blog post
- [ ] Click on related posts - should navigate correctly
- [ ] Share blog post (if share buttons exist)
- [ ] Comments work (if enabled)

---

## Admin Pages

### 25. Admin Login Page
**URL**: `http://beta-test.rockae.com/admin/login`

**Visual Checks:**
- [ ] Login form is visible
- [ ] Form is properly styled
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Enter admin credentials
- [ ] Login successfully - should redirect to admin dashboard
- [ ] Try invalid credentials - should show error
- [ ] Regular user cannot access admin features

---

### 26. Admin Dashboard
**URL**: `http://beta-test.rockae.com/admin/dashboard`

**Visual Checks:**
- [ ] Dashboard shows statistics and metrics
- [ ] Navigation menu is visible
- [ ] All sections are accessible

**Functionality Tests:**
- [ ] View application statistics
- [ ] Navigate to different admin sections
- [ ] Manage users
- [ ] Manage communities
- [ ] All admin features work as expected

---

### 27. Blog Management Page (Admin)
**URL**: `http://beta-test.rockae.com/admin/dashboard/blogs`

**Visual Checks:**
- [ ] Blog list/table is visible
- [ ] Create/Edit/Delete buttons are visible
- [ ] Page is responsive

**Functionality Tests:**
- [ ] Create new blog post
- [ ] Edit existing blog post
- [ ] Delete blog post
- [ ] Publish/unpublish posts
- [ ] All CRUD operations work correctly

---

## General Testing Notes

### Cross-Browser Testing
- [ ] Test on Chrome (latest version)
- [ ] Test on Firefox (latest version)
- [ ] Test on Safari (latest version)
- [ ] Test on Edge (latest version)
- [ ] Test on mobile browsers (Chrome, Safari on iOS)

### Responsive Design Testing
- [ ] Desktop (1920x1080, 1366x768)
- [ ] Tablet (768x1024)
- [ ] Mobile (375x667, 414x896)

### Performance Testing
- [ ] Page load times are acceptable (< 3 seconds)
- [ ] Images load properly (no broken images)
- [ ] No console errors in browser dev tools
- [ ] No network errors (check Network tab)

### Accessibility Testing
- [ ] All buttons and links are keyboard accessible
- [ ] Form fields are properly labeled
- [ ] Images have alt text
- [ ] Color contrast is sufficient
- [ ] Screen reader compatibility (if possible)

### Security Testing
- [ ] Authentication redirects work correctly
- [ ] Unauthorized access is prevented
- [ ] CSRF tokens are present (if applicable)
- [ ] Sensitive data is not exposed in URLs (unless intended)
- [ ] Logout clears session properly

### Error Handling
- [ ] 404 page displays correctly for invalid URLs
- [ ] Error messages are user-friendly
- [ ] Form validation errors are clear
- [ ] Network error handling works

---

## Testing Checklist Summary

**Before Starting:**
- [ ] Clear browser cache
- [ ] Test with fresh account
- [ ] Have test email account ready
- [ ] Test in incognito/private mode for some tests

**Critical Paths to Test:**
1. Sign Up → Email Verification → Sign In → Create Community → Add Content
2. Sign In → Join Community → Post in Town Hall → Reply to Posts
3. Sign In → Create Classroom → Add Content → Share URL → Open URL in new browser

**Common Issues to Watch For:**
- Pages not loading
- Forms not submitting
- Images not displaying
- Mobile layout breaking
- Navigation not working
- Deep links not working
- Email notifications not arriving
- Data not persisting after save

---

**Last Updated**: [Current Date]
**Test Environment**: beta-test.rockae.com
**Document Version**: 1.0
