// $Id$

********************************************************************************
********************************************************************************

*****************
*  INFORMATION  *
*****************

 Email FileField:  email_filefield.module
  
--------------------------------------------------------------------------------
 DESCRIPTION
 
 
 Defines a CCK file field formatter that allows for the 
 emailing of files attached to content.

--------------------------------------------------------------------------------

 This project is managed with:
 
 1. Git [ http://git-scm.org ] - Source management
 2. GitHub [ http://github.com ] - Main project space
 3. CVS [ http://cvs.drupal.org ] - Shortly as a Drupal project
 
 
 developed by: 
 
   1. CollectiveColors - http://collectivecolors.com
   
   ------------------------
   
   * Contact us if you are interested in co-maintaining.
   
   * See commit history for project if you are interested in actual development
     breakdown by maintainer.
 
 
 project home: 

   http://github.com/collectivecolors/drupal-modules-email_filefield


 test environment: 

   http://github.com/collectivecolors/drupal-sites-email_filefield_test


********************************************************************************
********************************************************************************

******************
*  INSTALLATION  *
******************

 Currently this module requires the following Drupal modules be installed
 and enabled.
 
   * filefield  -  http://drupal.org/project/filefield
   
   * thickbox   -  http://drupal.org/project/thickbox
   
   * webform    -  http://drupal.org/project/webform
   
--------------------------------------------------------------------------------
 TO INSTALL VIA GIT
--------------------------------------------------------------------------------
 START BY:

 [1]$ cd $TOP_LEVEL_SITE_DIRECTORY
 
 -------------------------------------------
|  To clone this module into a Drupal site  |
 -------------------------------------------
  THEN DO THIS:
 
   # Only if your Drupal project << IS NOT >> a GIT REPOSITORY!!!
 
 [2]$ git clone git://github.com/collectivecolors/drupal-modules-email_filefield.git 
                sites/all/modules/email_filefield

 --------------------------------------------
|  To import this module as a Git submodule  |
 --------------------------------------------
  OR DO THIS:
  
   # Only if your Drupal project << IS >> a GIT REPOSITORY!!!
              
 [2]$ git submodule add git://github.com/collectivecolors/drupal-modules-email_filefield.git
                        sites/all/modules/email_filefield
                        
 [2.1]$ git commit -m "Adding email_filefield module to project."

---------------------------------------------
 THEN CONTINUE WITH:
 
 [3]$ cd sites/all/modules/email_filefield
          
 [4]$ git checkout -b $MY_BRANCH $MODULE_TAG   
    
    # For example, $MY_BRANCH  = dev
    # For example, $MODULE_TAG = DRUPAL-6--1-0-BETA1
      
 [5]$ git status # Your ready for site configuration ( See below )


********************************************************************************
********************************************************************************

*******************
*  CONFIGURATION  *
*******************

1. Once you have the module directory copied into your sites/all/modules 
   directory, the make sure the "FileField Email Formatter" is enabled in the 
   admin/build/modules page.


2. Create a webform to use as your email message form.  You may have whatever
   components you want as long as you follow a few simple rules.

  * Create at least one email field within your webform and check the box
    "E-mail a submission copy" within the component field edit form.  This will 
    make sure that the emails entered into these fields will receive the files.
    
  * Check "Email" for any fields that you wish to be transmitted in the email 
    message from the webform.  The contents of the message are themable, but 
    this gives you some defaults to work with.
    
  * Do not use multi page forms for email form webforms.
  
  * The submission message can be set by setting the "Confirmation message"
    setting in the main webform edit page.  Begin your message with:
    "message: ".
    
      For example: "message: Your file has been sent."
      
  * The from information from the webform is used as the from in the file email.
  

3. Create your content type filefields or go to the filefield edit page within 
   the content type, you wish to use the email form formatter on. You will 
   notice some settings for this formatter near the bottom of the form in a 
   section titled "Email formatter settings".  Change these to suitable values.

  * Select the webform you wish to use for this email form.  Remember not to use
    webforms that do not contain at least one email field with the 
    "E-mail a submission copy" option checked.  You will probably want some 
    kind of message field as well.
    
  * Set the height and width of the thickbox display.  This display is centered
    on the page.  You may need to adjust these values depending on the size of 
    your form.  If the display is too small, you will get the dreaded scrollbars
    of death.  As far as I know, that is a thickbox issue.

 
4. Select to use the email form formatter on the field display edit page within
   the content type edit section.  You will see it listed as 
   "Link with popup email form" in the formatter select boxes for the teaser and 
   body.


5. If you want you can theme the filefield formatter output.  There are a lot of
   theme functions that allow you to craft the display to your liking.  The same
   is true of the email that is generated.

6. Let us know if you have problems.  Until we get this posted on Drupal, we
   will be using the issue queue at:

  http://github.com/collectivecolors/drupal-modules-email_filefield/issues
  
  * Please post any issues you have with this module there.


********************************************************************************
********************************************************************************
