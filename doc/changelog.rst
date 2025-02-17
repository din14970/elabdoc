.. _changelog:

Changelog
=========

Version 3.6.7
-------------

Security:

* Update PrismJS dependency to prevent ReDoS

Bugfixes:

* Fix issue with incorrectly encoded characters preventing display of content
* Fix performance issue with API when fetching entities
* Fix bug where API would send back only 16 items (#2345)

New features:

* Add /tags API endpoint (fix #2495)

Please note that the current patches are light, but that's because the goal here is to have a stable 3.6 branch before 4.0 comes along and breaks everything (minimum php version 8.0 and MySQL 5.7). There are a lot of changes cooking in the hypernext branch ;)

Version 3.6.6
-------------

Vulnerability fix:

* Prevent Regular expression Denial of Service by upgrading "marked" library.

Enhancement:

* Make URLs imported through CSV clickable

Version 3.6.5
-------------

Bugfixes:

CRITICAL bugfix: in certain conditions, tags could be removed from experiments when deleting items, and vice-versa. Not anymore.

Version 3.6.4
-------------

Bugfixes:

* Fix issue with SAML when using several IDPs
* Fix sorting/filtering issue on related experiments view

And some dependencies updates.

Version 3.6.3
-------------

Bugfixes:

* Fix issue with SAML auth user creation (#2344)
* Fix issue where complicated passwords would not work anymore
* Fix search page dropdown list for "Search in" (#2347)

New features:

* Allow connecting to a MySQL server in SSL context

Docker image:

* Use s6-overlay instead of supervisord to start services

Version 3.6.2
-------------

Bugfixes:

* Fix TODOlist minor issues (#2346 by Marcel Bolten)
* Fix password reset save button sometimes not showing
* Fix incorrect status list on search page (#2295)
* Fix notice in logs if saml_team is not set

Enhancements:

* Order groups by name (#2264)

i18n:

* Add missing translations and refresh translations
* Make permissions translated (#1901)

Dependencies:

* Upgrade to webpack 5
* Upgrade some php libraries

Version 3.6.1
-------------

Bugfixes:

* Avoid 2FA setup failed attempts count (#2342 by Marcel Bolten)
* Restore admins possibility to disable 2FA (#2341 by Marcel Bolten)

Version 3.6.0
-------------

Here it is, the 3.6 branch featuring LDAP and 2FA authentication!

Possibly breaking change:

Due to a weird naming convention in Swiftmailer, the library used to send emails, it is possible that you will need to change the port for the SMTP server. This probably won't impact you as what you are probably doing now is using STARTTLS on a TLS capable port.

See #2229 for more information. Test emails after upgrading.

New features:

* Add LDAP authentication
* Add 2FA authentication with OTP (contribution by Marcel Bolten)
* Allow description list html elements (#2308 by Marcel Bolten)

Bugfixes:

* Fix template import (#2283)
* Fix issue with booking to sunday midnight (#2211) and allow all hours
* Fix display of markdown in show mode (#2231)
* Fix timestamp on generated PDF (#2210 contribution by scapoor)
* Allow changing an upload if we have write rights on entity (#2292)
* Fix incorrect permissions on template creation (#2237)
* Fix image quality after upload for .jpg files (#2186)
* Fix lock icon sometimes not clickable in view mode
* Fix incorrect proxy setting preventing loading of sysconfig panel

Enhancements:

* Align icons and text in main menu drowdown (#2269)
* Fix editable triggered on non editable comments
* Save title and date on title blur
* Prevent clickable .tif thumbnail (#2212)

i18n:

* Translate "Click to edit"

Dev corner:

* Rewrite download.php into a proper controller and use http-foundation
* Add new unit tests
* Rewrite all authentication related code; add all the Auth services
* Specify the ISO::8601 date format for scheduler
* Rationalize the tinymce config (#2239)
* Rewrite interfaces to be more modular (#2238)
* Move around a bunch of code to delete some controllers
* Make more TypeScript classes for CRUD actions
* Add a "big" database generator (lots of fake content)

Version 3.5.6
-------------

The sixth patch for 3.5. Go get your 8 bugfixes ASAP! If you're running 3.5.(1|2|3|4|5), upgrade now! If you're not, upgrade nonetheless ;)

See the `changelog for 3.5.0 <https://github.com/elabftw/elabftw/releases/3.5.0)>`_ if you're not already on 3.5.0.

Bugfixes:

* Fix experiments from team showing up on category filter
* Disable contextual menu in tinymce (#2207)
* Fix next step display (#2206)

Version 3.5.5
-------------

The fifth patch for 3.5. Go get your 8 bugfixes ASAP! If you're running 3.5.(1|2|3|4), upgrade now! If you're not, upgrade nonetheless ;)

See the `changelog for 3.5.0 <https://github.com/elabftw/elabftw/releases/3.5.0)>`_ if you're not already on 3.5.0.

New:

* `Planted 1022 trees <https://ecologi.com/deltablot>`_

Bugfixes:

* Fix checkbox staying selected in show mode after deletion (#2185)
* Fix image edit bug with TinyMCE (#2183) contribution by Sherjeel Shabih
* Fix next step display not following ordering
* Fix event from another team not showing up in scheduler
* Fix permissions on database item in some cases (#2189)
* Fix unfinished steps sorting in todolist (#2169) contribution by Marcel Bolten
* Fix unselectable single column layout setting in UCP (#2167) contribution by Marcel Bolten
* Fix invisible teams still visible in anon login on login page

Version 3.5.4
-------------

The fourth patch for 3.5. If you're running 3.5.(1|2|3), upgrade now! If you're not, upgrade nonetheless ;)

See the `changelog for 3.5.0 <https://github.com/elabftw/elabftw/releases/3.5.0)>`_ if you're not already on 3.5.0.

Bugfix:

* Fix bad template on UCP

Version 3.5.3
-------------

The third patch for 3.5. If you're running 3.5.(1|2), upgrade now! If you're not, upgrade nonetheless ;)

See the `changelog for 3.5.0 <https://github.com/elabftw/elabftw/releases/3.5.0)>`_ if you're not already on 3.5.0.

Enhancements:

* Fix bad performance on experiments show mode
* Improve the Templates class code

i18n:

* Update Chinese translations


Version 3.5.2
-------------

The second patch for 3.5. If you're running 3.5.1, upgrade now! If you're not, upgrade nonetheless ;)

See the `changelog for 3.5.0 <https://github.com/elabftw/elabftw/releases/3.5.0)>`_ if you're not already on 3.5.0.

Bugfix:

* Fix issue with leftover pinned items if user deleting it is not the one who pinned it (#2158)

Enhancements:

* Greatly improve the performance on team and ucp pages with templates
* Revamp how the templates are displayed and group them by owner (#2157)

Version 3.5.1
-------------

The first patch for the 3.5 branch!

See the `changelog for 3.5.0 <https://github.com/elabftw/elabftw/releases/3.5.0)>`_ if you're not already on 3.5.0.

Bugfixes:

* Fix not all bookable items showing on Team page (#2128)
* Fix incorrect permissions left hanging after deletion of a team group
* Fix public, organization and team group where current user is not showing up in show mode as expected
* Fix changing permissions broken notification bubble
* Make sure acs url for SAML works with a / at the end of the url setting (#2117)

Enhancements:

* Display team group(s) appartenance on profile page
* Add eLabFTW version in footer
* Add the permissions link if we don't own the experiment (#2132)
* Upgrade some dependencies to the latest version (like Mathjax 3.1.0)
* Use one deduplicate button on the tag manager to deduplicate all tags at once (#2137 #2118)
* Improve tag manager user experience


Version 3.5.0
-------------

This is a major update. After updating the container, you will need to run the update script:

.. code-block:: bash

   # with docker
   docker exec -it elabftw bin/console db:update
   # without docker
   php bin/console db:update

**Breaking changes**:

If you are using Docker (and you should :p), the access and error logs are now sent to stdout and stderr of the container. So if you were using `/var/log/nginx/access.log` and `/var/log/nginx/error.log` to store the logs, you will now need to use `docker logs elabftw` to see them. Use `docker logs elabftw 1>/dev/null` to see only errors and `docker logs elabftw 2>/dev/null` to see only access log. This change was done to align with docker best practices and should facilitate central logging.

**New features**:

* Enforce read/write permissions of experiments by Admin (#1999)
* The Todolist is now also showing the unfinished steps in experiments (#2024)
* The Todolist will stay open on page change
* External authentication (contributed by @manu0401) (PR #2023). If the webserver is providing authentication, use this to login the user. Also provide an URL for logout. Add parameters in Sysconfig page to configure external auth
* Add proper Single Log Out (#1691)
* Steps on experiments are now sortable and editable (#904)
* Add pinned entities. A pinned experiment or item will stay on top of the page in show mode
* Add Ctrl+= and Ctrl+Shift+= for subscript/superscript (#1556)
* Add JSON export from show mode
* Generate a single PDF file with all selected items (PR #2038) (#434) Contribution by Marcel Bolten
* Show related items in view/edit mode (PR #1993) (#1432) Contribution by Marcel Bolten
* Allow file upload with copy/past (PR #1886) Contribution by Sherjeel Shabih
* Display a link to the scheduler on experiments bound to a scheduler event
* Order the links by name (#1940)
* Add template permissions similar to exp/items permissions (PR #1885) (#1668) Contribution by Max Schröder and Farrukh Faizy
* Allow hiding a team from the register select

**Enhancements**:

* Make one less SQL request on page load if admin
* Use correct background color for events on creation in scheduler
* Allow several whitelisted email domains (#1836)
* Display Mathjax in preview mode of markdown editor (#892)
* Add the filter/order/sort/limit menu on Search page
* Add a Tag input in show mode to look for tags
* Increase the size limit of hashed files on upload
* Don't try to rotate tif files (#2071)
* Logout user after use of an eLabID link
* Add month view in scheduler
* Show templates from other teams on Team page (#1457)
* Hide the import button from Links in templates (#1745)
* Make the Todolist push the content to the right (#1871)
* Fix the Json editor +/- button when loading a file
* Prevent Tinymce from showing raw html on editor load
* Don't show the Tags line in pdf in there are none
* Use bootstrap-select in some selects so the options can be filtered
* Send notif to user that needs validation and send user info to admin(s)
* Change min delta characters for revision create from 20 to 100 (helps reduce the db size growth). Might be configurable later on
* Add json viewer on view mode (contribution by Sherjeel Shabih) (#2100)
* Fix HTML syntax violations (contribution by Marcel Bolten) (#2099)
* Fix disappearing 3D molecule after new upload or delete (#2094) by Marcel Bolten
* Rework the templates (#2095)
* Add "save as" option for JSON editor (contribution by Sherjeel Shabih) (#2108)

**i18n**:

* Several new strings translated. Add i18next library to translate in javascript

**Bugfixes**:

* Fix wrong IDP used when several active IDPs were configured
* Fix potential issues spotted by static analysis
* Fix count of experiments in report (#2025)

**Updates**:

* Update prismjs

**Docker**:

* Add possibility so configure a user and group for nginx. This is useful if you're using a server picky about users (using NFSv4 for instance). A contribution by François Prud'homme.

**Developer corner**:

* Add Elabftw\Maps\Team and UserPreferences. Maps are classes that map their properties to columns in a table. This is a work-in-progress.
* Add Elabftw\Elabftw\DisplayParams to store order/query/limit/offset/sort of show mode
* Make a single JS bundle instead of one per page and use "defer" to load it
  before: 6141134 bytes of JS
  after: 5560564 bytes of JS
* Overall code quality improved. Previous rating on scrutinizer-ci was 8.7, it is now 9.09!


Version 3.4.17
--------------

IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!


IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!

This patch fixes a CRITICAL vulnerability in the way the login mechannism works. It is STRONGLY recommended to update to this version as soon as possible.

Security fixes:

* Fix CRITICAL issue with login (thanks Marcel Bolten)
* Fix vulnerabilities in jsoneditor

Version 3.4.16
--------------

IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!


IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!

Bugfixes:

* Fix issue where database item edited by someone from another team would appear in that team instead of staying in the original team
* Fix incorrect experiments count in sysadmin report (#2025)

Version 3.4.15
--------------

IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!


IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!

Bugfix:

* Fix admin could not edit user from own team

Version 3.4.14
--------------

IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!


IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!

Bugfix:

* Fix the need to reload the page after adding a link for actions (#1943)

Version 3.4.13
--------------

IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!


IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!

Enhancement:

* Only save a revision if there are at least 100 characters of difference (previously was 20)

Bugfixes:

* Fix impossibility to send mass emails
* Fix user able to unlock entity if locked by someone else (#1967)

Version 3.4.12
--------------

IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!


IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!

This is just a small patch fixing one bug.

Bugfix:

* Fix experiment/item not showing up in show mode if read permission is set to 'user' (#1956)

Version 3.4.11
--------------

IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!


IMPORTANT: read the `changelog for 3.4.0 <https://github.com/elabftw/elabftw/releases/3.4.0>`_ if you're updating from 3.3.x!

This release is all about SPEED. The loading time of big databases should be much faster now and take up less resources.

This patch doesn't contain database changes, so there is no need to run the `db:update` command after updating.

Bugfixes:

* Fix incorrect link on tags displayed on search page
* Fix the documentation link for postinstall in sysadmin page

Enhancements:

* Drastic page load speed improvements (#1941)
* Add male and female signs to charmap plugin in tinymce
* Allow user creation even if local register is disabled (#914)
* Add a button to go back to view mode from edit mode

Version 3.4.10
--------------

IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!

IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!

IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!

IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!

This patch doesn't contain database changes, so there is no need to run the `db:update` command after updating.

Bugfixes:

* Remove the tag cloud from the Team page because it's slowing down the page too much with a big database
* Fix CSS of mol importer button in molecule editor

Enhancements:

* API will properly return 404 error if a resource is not found (update to elabapy coming later)
* API documentation has been vastly improved with many examples
* Reduce table padding so it doesn't appear too wide in view mode compared to edit mode

Dev:

* Update javascript and PHP dependencies.

Version 3.4.9
-------------

IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!
IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!
IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!
IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!
IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!
IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!
IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!
IMPORTANT: read the changelog for 3.4.0 if you're updating from 3.3.x!

This patch doesn't contain database changes, so there is no need to run the `db:update` command after updating.

Bugfixes:

* Fix the need to reload page to toggle lock (#1897)
* Fix reset password button appearing greyed out (#1902)
* Make sure the teams exist before creating user in SAML auth (#1896)
* Fix tables in markdown (#1323)
* Fix comment not saved if the email is not configured (#1884)

Enhancements:

* Add the teams in the report (#1882)
* Fix alignment of top right menu (#1889)
* Add user panel link in footer (#1888)
* Display last modification time (#1883)
* Increase uploader timeout
* Add "Clear all" button on search page (#1910)
* Remove HTML/XML syntax highlighter (#1909)
* Reload page after lock (#1897)

i18n:

* Localize prompt when booking an item (#1903)
* Fix the localization of scheduler (#1903)
* Add translation for "Show more" and "Switch editor" (#1899 #1900)
* Add missing "Privacy policy" translation (#1872)
* 100% translated in Chinese, Japanese, Korean, Russian, Italian, Dutch, French, German
* Fix localization of text editor

Dev:

* Use rector to find issues in code
* Psalm now reports 0 errors and 0 warnings with the highest setting

Version 3.4.8
-------------

See changelog for version 3.4.0 for breaking change if you're upgrading from 3.3.x version!

Bugfixes:

* Fix issue where an admin could not validate a team member
* Fix users appearing n times in sysadmin panel if member of n teams
* Fix incorrect number of exp/items displayed in certain conditions

Version 3.4.7
-------------

See changelog for version 3.4.0 for breaking change if you're upgrading from 3.3.x version!

Bugfixes:

* Fix issue where team groups where not restricted to teams
* Fix issue where not enough experiments were displayed for some users (#1854)
* Fix filename on download for CJK characters (#1830)

New feature:

* Allow ordering by last modification time (#1734)

Enhancement:

* The "Back to listing" button will keep the previous filters

Documentation:

* Add documentation for "bookable" and "backupzip" API endpoints (#1866)

i18n:

* Fix missing translations and update italian (thanks @topoldo) (#1859 #1858)

And upgrade some JS and PHP dependencies.

This patch doesn't require an SQL update.

Version 3.4.6
-------------

See changelog for version 3.4.0 for breaking change!

Bugfixes:

* Fix database toggle lock permission issue (#1855)
* Fix the register link in German (#1856)

i18n:

* Update translations

Version 3.4.5
-------------

See changelog for version 3.4.0 for breaking change!

Bugfix:

* Fix quicksearch on Database (#1853)

Version 3.4.4
-------------

See changelog for version 3.4.0 for breaking change!

Security:

* Fix security vulnerability in Symfony http-foundation library
  https://github.com/advisories/GHSA-mcx4-f5f5-4859

Bugfixes:

* Fix some experiments not showing up (#1852)
* Fix date fields on search page and anon search

i18n:

* Update translations


Version 3.4.3
-------------

See changelog for version 3.4.0 for breaking change!

Bugfixes:

* Fix issue with permissions being too open (#1834)
* Fix issue where toggle password was activated by pressing enter in login fields
* Prevent removing team of user in only one team (#1835)

Enhancements:

* Prevent deletion of users with experiments (#1817)


Version 3.4.2
-------------

See changelog for version 3.4.0 for breaking change!

Hotfix for database upgrade.

Version 3.4.1
-------------

See changelog for version 3.4.0 for breaking change!

Bugfix:

* Fix issue with update (see #1832)

Enhancement:

* Add possibility to display the password in password fields on login and register page (#1823)


Version 3.4.0
-------------

Wow. This is a BIG update! A lot of commits, new features, enhancements and general code improvements. eLabFTW keeps improving thanks to the community of users and people sponsoring the project through donations (on liberapay.com) or custom development requests (on deltablot.com).

.. warning:: This version requires a change in the MySQL structure. After the update, run `bin/console db:updateTo34`.

How to update the SQL structure:

.. code-block:: bash

    # for docker users (assuming the container is called 'elabftw'
    docker exec -it elabftw bin/console db:updateTo34
    # for non docker users (from the elabftw folder)
    php bin/console db:updateTo34

`Read the blog post for this release! <https://www.deltablot.com/posts/release-340/>`_

Bugfixes:

* Fix files not getting imported from zip archive (#1645)
* Fix wrong behavior on InvalidSchemaException
* Fix the division by zero warning for new user visiting profile
* Fix registration emails not sent to admins with lock power

New features:

* Allow users to be in several teams
* Add write permissions to exp/items
* Remove team restriction on team groups: you can add a member of another team in a team group
* Add possibility to create users from the sysadmin/admin panels
* Allow TAB separated values for CSV import (#1743)
* Add expand all button (#1634)
* Upgrade of the Scheduler with new version, better UI and possibility to bind an experiment to an event (#1619)
* Add JSON editor (by @shabihsherjeel via PR #1554) (fix #1467)
* Allow sysadmin to restrict email domain on registration (#1649)
* Add API access to events and bookable endpoints (#1618)
* Add API endpoint for making a zip backup on a time period
* Improve the permission system with separate read/write permissions (#1646)
* Allow IDP to send several teams and synchronize the teams from that

Enhancements:

* Import steps and links from zip archive (#1645)
* Add the user menu in the navbar
* Place the Create button on the right side and improve it
* Resize the main container
* Add modal dialogs for timestamping, create item and help
* Improve zip name for single export (#1690)
* Allow visibility change in show mode for items (#1640)
* Make todolist scrollable (#1626)
* Read exif orientation of image and rotate it if necessary (#1635)
* Improve the UI of login and register pages
* Background color of events is now color of item type (#1672)
* The database structure import is now done through a command instead of the /install folder
* Add pretty modals for some actions
* Update Italian
* Increase timeout for uploading big files
* Make the main container less wide
* Move the menu into the top bar

Developer:

* Add dev:populate command to replace the current database with fake data
* Improve the test suite to use a temporary docker setup to run the tests (see `tests/run.sh`)
* Use Codeception to run API tests instead of a custom curl script
* All Javascript has been moved to TypeScript (in `src/ts`)
* All CSS has been moved to SCSS (in `scr/scss`)
* The webpack packing has been greatly improved with proper chunking (see `builder.js`)
* Update Codeception to 4.0
* Bootstrap is now used properly with SCSS variables overriding and proper usage of bootstrap classes for buttons

Version 3.3.12
--------------

Security:

* Upgrade SAML library. Fix https://github.com/advisories/GHSA-pqm6-cgwr-x6pf

New feature:

* Add japanese language: thanks to Yoshihiko Kunisato!

Enhancement:

* Display all bookable items by default on scheduler (#1453)
* Add possibility to connect on non standard Mysql port
* Prevent password reset on unvalidated accounts (#1572)

Bugfix:

* Fix database items not deletable if sysadmin disabled deletion of experiments for everyone

Updates:

* Upgrade Mathjax to version 3
* Upgrade Tinymce to 5.1

Version 3.3.11
--------------

New feature:

* Add several new API endpoints to create database items and list item types and status
  See the documentation for usage: https://doc.elabftw.net/api.html and https://doc.elabftw.net/api/
  This feature was sponsored by Mark Greiner from the Max Planck Institute for chemistry energy conversion:
  https://cec.mpg.de/en/research/heterogeneous-reactions/dr-mark-greiner/

Bugfixes:
* Remove the share button on database item (fix #787)
* Fix file upload through API

* Update dependencies

Version 3.3.10
--------------

This patch does NOT need to update the MySQL structure (with the db:update console command).

Bugfixes:

* Fix SMTP password getting blanked if email settings were changed
* Fix files not getting imported from zip archive (#1537)
* Fix the double 'tag' css class on tags
* Fix missing files for mobile editor

Enhancements:

* Add alert if the body contains too many characters
* Improve the filtering of characters for filesystem output
* Use TinyMCE's autosave plugin
* Add next step and comments icon in show mode for items (#1447)

Version 3.3.9
-------------

This patch doesn't need to update the MySQL structure (with the db:update console command).

Bugfixes:

* Copy links and steps when duplicating an template (#1465)
* Fix editor issue with mobile browsers (#1316)
* Fix wrong page redirection upon archive toggle of user
* Fix bug report URL (#1507)

Enhancement:

* Add steps and links to template view in team tab

New features:

* Add a link on the Team template page to create experiment directly from that template
* Allow import of body of linked item (#1533)
* Add Insert Template menu item in TinyMCE editor to load from template (#1428)

Version 3.3.8
-------------

Bugfixes:

* Fix install process
* Fix "order by" menu in database tab (#1447)

Enhancement:

* Add limit in top right menu so the other parameters stay there

Version 3.3.7
-------------

Another patch for 3.3 version with one major bugfix and two minors.

All users should update. No database schema update required.

Bugfixes:

* Fix the top right menu in show mode showing no results (#1447)
* Fix the tag filter lost on filter/order/sort search (#1436)
* Fix 0 rating on items (#1182)

Enhancements:

* Add SameSite attribute to cookie (#394)
* Increase the size of the tags box on search page (#1437)

Dev corner:

* Improvements in the code to bring psalm errors/warnings to 0.
* Add configuration for phpstan, phan and psalm, with corresponding yarn commands


Version 3.3.6
-------------

A few bugfixes and a new feature: you can now share an experiment/item with a share link that will unconditonally give read access to whoever has it.

Bugfixes:

* Fix autocompletion (with '#' character) (#1359)
* Fix Javascript errors in Microsoft Edge (#1336)
* Fix 'moment' library internationalization
* Fix incorrect handling of thumbnail if the file is too big
* Fix HTML tags closing
* Fix limit selector on search page
* Fix tag search being too inclusive (#1204)
* Fix permissions issue with 'organization' visibility (#1389)

New features:

* Add share button (#1396)

Enhancements:

* Add color to clickable title
* Add blockquote CSS
* Add links and steps in API GET results (elabftw/elabapy#7)
* Update DFN certificates (#1414)
* Add possibility to unarchive users (#1424)
* Improve results per page select element (#1354)
* Update dependencies

Version 3.3.5
-------------

This is mostly a maintenance release with bugfixes from dependencies. TinyMCE (the text editor) has fixed numerous little bugs, there is also an update of the library parsing Markdown (marked) that had a ReDOS vulnerability (Regular Expression Denial Of Service) and an update of the SAML2 library with some bugfixes and new features.

On eLabFTW side, the library to convert markdown (the PHP one) has been changed to league/commonmarkconverter.

To update: just update the container and that's it. No need for database update.

Version 3.3.4
-------------

This release doesn't need a MySQL schema update. Simply updating the container is enough.

Bug fix:

* Update JS dependencies because 0.7.2 of faye/websocket-driver was pulled off and it is the version in yarn.lock
* Fix login as anonymous user

New feature:

* Add Dutch (nl_BE) lang: thanks to Philip Plaeke

Enhancement:

* Load CSS assets with version string (force browser cache bust)


Version 3.3.3
-------------

Bug fix:

* Improve the pagination logic and user interface in show mode (#1345)

Enhancements:

* Update Korean translations

Version 3.3.2
-------------

Bug fix:

* Fix issues with permissions where only a few experiments would be displayed to non admin users in certain conditions (#1337)

Enhancements:

* Make the space in quicksearch bar behave as AND (#1277)
* Display full content of calendar event on mouse hover (#1320)
* Add some security options for SAML (#1339)

Version 3.3.1
-------------

Bug fixes:

* Fix issues with permissions where only a few experiments would be displayed to non admin users in certain conditions (#1337)
* Fix steps/links not working on templates other than first one (#1338)

Version 3.3.0
-------------

Note: read the release notes of 3.0.0 if you're upgrading from v2.x!

Upgrading:

* After updating the docker image, run `bin/console db:update`
* For Docker users that would be: `docker exec -it elabftw bin/console db:update`
* For non-Docker users: `php bin/console db:update`

Bug fixes:

* Fix error in the nginx log about content.css file missing (#1321)
* Fix table header html tag (th) that was stripped (#1324)
* Fix markdown tables not working (#1323)
* Fix pasting from Excel/Libreoffice calc (#1331)

New features:

* Add Korean translation: thanks to Jihun Kim!
* Add Steps and Links to Database items and Experiments templates (#492)
* Add user setting to allow only member of same group to edit experiment (#851)
* Add announcements for sysadmins to display a message to all users (#1248)
* Allow complete blockage of experiment deletion (#1281)
* Allow saving mol files as png (#996)
* Allow admin to select the CSV separator for import
* Add bug report icon in footer

Enhancements:

* Add proper locking mechanism to items (#1049) Note: all previously locked items (in Database) will be unlocked!
* Move the API keys manager from profile to user control panel
* Allow reset of privacy policy
* Add left border color to items too

Docker:

* Remove the form-action CSP directive (#1322)

Dev corner:

* Symfony 4.3
* Use symfony/process for timestamping
* Add PHP-CS-Fixer rules

Version 3.2.2
-------------

Note: read the release notes of 3.0.0 if you're upgrading from v2.x!

This is a small patch to the 3.2.1 version.

Bugfix:

* Fix incorrect check on deletion of linked item (#1298)

Version 3.2.1
-------------

Note: read the release notes of 3.0.0 if you're upgrading from v2.x!

This is a small patch to the 3.2.0 version.

Bugfixes:

* Fix molecules not displayed in edit mode after deletion of a file and partial page reload
* Fix tag destroy from Tag Manager in admin panel (#1291)
* Fix double referrer header

Enhancements:

* Display thumbnail of TIF files in PDF (thanks Temple)

Updates:

* Update TinyMCE to 5.0.6

Version 3.2.0
-------------

Note: read the release notes of 3.0.0 if you're upgrading from v2.x!

**Upgrading**:

This release needs a database schema update: run "docker exec -it elabftw bin/console db:update".

For non docker user: "php bin/console db:update".

Bugfixes:

* Fix default Welcome message showing up when it shouldn't in show mode (#1272)
* Fix team statistics on team page showing full stats instead of team stats
* Fix tagcloud tags links (#1267)
* Fix owner name appearing twice on search page (#1212)
* Fix lists not being properly styled (#1282)
* Fix sysadmin promotion (#1280)

Enhancements:

* Zip export is now streamed to the browser
* Display molecule in edit mode (#1166)
* Improve user interface

New features:

* Allow ordering by id in show mode (#1277)
* Ask user for filename when saving molecule or doodle (#1166)
* Add new options for IDP config: toggle team creation and set default team (#985)
* Allow users to load uploaded mol files from the load menu of the molecule editor (#1166)
* Add a command to ligthen the revisions tables that are too big (see #623) => bin/console thanos:snap
* Add main toggle for SAML login

Dev corner:

* Refactor the Make family and get rid of the make.html template
* Remove Colorpicker and use input type = color
* Add CsvTrait
* Add more acceptance tests
* Fix some issues found by phpstan and psalm

Version 3.1.2
-------------

Note: read the release notes of 3.0.0!

Minor breaking change for users:

* Autocompletion for links in text is now only triggered by '#', not '$' anymore (conflict with Mathjax)

Bugfix:

* Fix items types update (#1265)
* Fix boxfile for Nanobox.io deployments

Enhancements:

* Make the autocompletion load faster for big databases


Version 3.1.1
-------------

Note: read the release notes of 3.0.0!

Bugfix:

* Fix actions (add/remove) in teamgroups (#1254)


Version 3.1.0
-------------

Note: read the release notes of 3.0.0!

Bugfix:

* Fix tag link in view mode (#1239)

Enhancements:

* Improve user experience when nothing is selected on show mode (#1232)
* Hide select menu if user clicks Unselect all (#1232)
* Use TinyMCE v5.0 (#1229)

Dev corner:

* Use codeception v3.0 (#1236)


Version 3.0.3
-------------

Note: read the release notes of 3.0.0!

Bugfix:

* Skip the mysql constraint on `users2teamgroups` table as it is not cleaned and can cause errors during upgrade

Version 3.0.2
-------------

Note: read the release notes of 3.0.0!

Bugfix:

* Fix password reset not working from Admin/Sysadmin panel (#1223)

Version 3.0.1
-------------

Note: read the release notes of 3.0.0!

Bugfix:

* Skip the mysql constraint on `tags2entity` table as it is not cleaned and can cause errors during upgrade

Version 3.0.0
-------------

Breaking changes:

* For users: Old API keys will be erased upon update. Users of the HTTP REST API will need to generate new keys from their profile.
* For sysadmins: If you are not using Docker you'll need to edit your CSP header and change google.com to gstatic.com!
* For sysadmins: To update the database schema, check the documentation guide: https://doc.elabftw.net/how-to-update.html#complete-upgrade-guide-from-2-7-0-to-3-0-0
* For non docker users: min PHP version is 7.2

New features:

* Add a report generating tool for sysadmin (#1000)
* Add support for Indonesian language (thanks to Khari Secario)
* Add possibility to send email to the team (#840)
* API keys are now stored properly and they have permissions (read/write or read-only)
* Add privacy policy setting in Sysadmin panel (#870)
* Add visibility setting to import CSV/ZIP (#988)
* Add "hr" plugin in tinymce for horizontal rules
* Add `bin/console` to manage updates and other things

Bugfixes:

* Fix issue with IDP of id different of 1, add active attribute to IDP (#1025)
* Fix insert in text at cursor position for markdown (#1094)
* Fix issue with multiple tag search and clicking a tag hiding the other tags (#974 #632)
* Correctly display markdown on revision page

Enhancements:

* API endpoint will send proper error codes instead of always 200
* Bring back the pretty pie chart on profile page. Note: if you are not using Docker you'll need to edit your CSP header and change google.com to gstatic.com!
* Add CSRF protection on basically every POST request
* Add recipients in BCC for mass email (#1021)
* The full users list is not displayed anymore on Sysconfig and Admin pages. A query must be entered (empty query will show all users)
* Add footer on search page when there is no search (#848)
* Set default font size in TinyMCE to 10pt (#880)
* Display the name of the author of revision (#924)
* Better warning message before deletion (#934)
* Add last login info for users (#1000)
* Add book link to view mode of bookable item (#847)
* Use marked instead of markdown-js to preview markdown (#1092)
* Allow admin to delete scheduler events of users in team (#1111)
* Add SECURITY.md file for security related information
* Add link to instance in email sent to admin after user registration (#953)
* Add gitter chat in footer
* Add documentation link on SAML config page (#1115)

Dev corner:

* Add more namespacing (for traits, models, controllers, services, exceptions and interfaces) and corresponding folders in `src/`
* Add new UploadTrait for common file operations
* Add new custom Exceptions, see Contributing page
* Update onelogin/php-saml to 3.0.0: drop the `mcrypt` PHP extension
* Get rid of the `src/views` classes
* Add new controllers in `src/controllers`
* Code style: don't check bool return value but expect exceptions if something goes wrong
* FormKey renamed in Csrf and added to App
* Remove `userid` property of Users
* Code style: don't catch exceptions, let them bubble up
* Code style: always use custom exceptions
* Add Extensions class to get the correct icon depending on extension
* Add MakeThumbnail to create thumbnails for uploaded files
* Split controllers in RedirectResponse and JsonResponse (Ajax)
* Add foreign keys constraints to the MySQL tables
* Change the update strategy: use sql files now
* Rename status (experiments) and type (items) columns in category
* Load prism.js from node_modules with webpack
* Better use of wepback for tinymce
* Add `tests/api.sh` for testing the HTTP API
* Load js from src folder if debug is on
* Numerous other small improvements to the code
* Add Contributor License Agreement for contributions
* Add a service to populate user data (very alpha for now) to work on a bigger database in dev
* Lint CSS with stylelint (see contributing doc)
* Lint JS with eslint
* Add .editorconfig and fix indentation discrepancies
* Add more tests in circleci (lint css, js and php)
* Remove jquery complexify from code and revamp the registration page

Version 2.0.7
-------------

* Fix files not getting deleted from disk
* Fix tags appearing multiple times

Version 2.0.6
-------------

Please read changelog for version 2.0.0 if you're upgrading from 1.8.5.

Bugfixes:

* Fix slowness in show mode if numerous tags, items
* Fix attached images in pdf files
* Fix issue with visibility update of database items

Version 2.0.5
-------------

Please read changelog for version 2.0.0 if you're upgrading from 1.8.5.

Bugfix:

* Fix issue preventing deletion of team groups (#977)

Version 2.0.4
-------------

Please read changelog for version 2.0.0 if you're upgrading from 1.8.5.

Bugfixes:

* Fix update visibility from show mode (#957)
* Fix bad ordering when using filters (#929)

Enhancements:

* Add Mathjax to show mode (#208)
* Prevent checkboxes from staying active in show mode (#890)
* Use trash icon for delete actions (#934)
* Better handling of failed SAML response

Maintenance:

* Update javascript and php dependencies

Version 2.0.3
-------------

Please read changelog for version 2.0.0 if you're upgrading from 1.8.5.

Bugfixes:

* Fix error when changing the role of a user (#874)
* Update TinyMCE and mPDF to latest stable version

Enhancements:

* Allow Sysadmin/Admin to change the team of a user if user has no experiments. Useful if user registered in wrong team. (#483)
* Add lang attribute to the page so the browser knows which language is displayed (#873)

Version 2.0.2
-------------

Please read changelog for version 2.0.0 if you're upgrading from 1.8.5.

Bugfixes:

* Fix template import issue (#863)
* Fix template destroy issue

Version 2.0.1
-------------

Please read changelog for version 2.0.0 if you're upgrading from 1.8.5.

Bugfixes:

* Fix # and $ autocomplete (#814)
* Don't display SwiftMailer error to user (#841)
* Make sure admin or sysadmin cannot change an email for an existing one (#809)
* Fix bad translation in french in UCP

Enhancements:

* Remove image upload button from TinyMCE toolbar to improve UX (#808)

And various small updates in dependencies.

Version 2.0.0
-------------

WARNING: BREAKING CHANGES IN THIS RELEASE!

Please read carefully these notes before upgrading your installation.

For Docker users: because you chose to use Docker, you have absolutely nothing to do, you can upgrade, sit back and relax. That's the advantage of using Docker: even if I move everything around in the image, for you it's transparent!

For non-Docker users: you need to perform manual steps in order to get your installation up and running for version 2.0.0. See the `Complete upgrade guide from 1.8.x to 2.0.0` on the :ref:`How to update <how-to-update>` page.

Why this update?
````````````````
Sometimes, you have to break things to make them better. With the version 2 I can remove support for php 5.6, allowing me to use the latest versions of some dependencies, and also type hinting, a new feature of the PHP language. I can move the web served directory to a separate directory that is not the root directory of the repo. This means the `uploads` folder is not in the webdir anymore which is better for several reasons. I can update different components to a major version (bootstrap, twig), use Webpack to deal better with the Javascripts, remove all the minified files from the git tracking. This means more work to install it without Docker, but the Docker method being the recommended one it's ok. It also means the repository is smaller and faster to clone. So basically with 2.0 I felt free to break everything and then rebuild it better after, without having to worry about anything (as long as I can write a proper upgrade documentation for non docker users!).

What changed?
`````````````

New features:

* Add Slovak lang − thanks to Martin Petriska from Bratislava
* Add 100% translated Russian lang − thanks to Mark T
* Database items now have comments (#508)
* Add option in user control panel to allow experiment edition from members of the team (#498)
* Allow creation of Links through API (#599)
* Add a Tag Manager in the admin panel so the admin can correct typos or remove tags (#715)
* Add Mathjax support for pretty mathematical expressions (#208)
* Add visibility to database items (#541)
* Add support for Nanobox.io deployment
* Add possibility to add a caption to inserted images (#241)
* Add Open Science mode allowing unregistered users to read experiments in a team (#718)
* Add EXPERIMENTAL feature for streaming zip archives (allows big zip) Enable it from UCP.
* Add option for french style signatures block in pdf (#726)
* Add possibility to download file through API (#798 #797)

Enhancements:

* Allow to search for tags with string from the middle of the tag (#702)
* Better user interface for Steps, Links and Todolist (#559)
* Show steps in view mode
* Use SVG icons instead of PNG
* Show owner in show mode if not current user for experiments (#616)
* Add relative moment for displaying a date
* Display locked date in view mode when hovering the lock icon (#189)
* Add Steps to PDFs (#189)
* Add more actions to the top right menu
* Page load is cleaner
* Add a version query string to assets to prevent caching of old versions
* Add more infos on Sysconfig page and reorganize the tabs
* Show 25 items instead of 10 for mention plugin (#641)
* Remove the 60 characters limit on autocomplete
* Updated translations
* Zip generation is less likely to fail

Bugfixes:

* Display edit icon in show mode for admins (#498)
* Fix permission issue when deleting experiment from show mode
* Fix order by category not working for experiments (#698)
* Fix revisions for admin (#662)
* Fix issues in SAML login if team is empty
* Fix tags not being imported when template is duplicated
* Fix steps/link not working with a '%' character (#791)
* Fix possibility to update category/visibility of locked item (#792)
* Fix issue with order by and sort (#790)
* Fix issue with comments (#802)

Dev corner:

* Minimum PHP version is now 7.1
* Update SwiftMailer to version 6
* Update Twig to version 2
* Update Bootstrap to version 4
* Use Webpack 4 to create bundles (using tree shaking feature to make smaller bundles)
* Use ES6 syntax for Javascript (const/let instead of var for instance)
* Drop phpdocumentor dependency in composer.json, use the phar instead
* Use type hinting
* Use strict_types
* Replace strlen() by mb_strlen()
* Use dirname(__DIR__) instead of relative paths
* Move the `cache` folder outside of `uploads`
* Split code in `web` and `src` folders
* Function signatures are more coherent
* Use random_bytes() to get random numbers
* Use chromedriver for acceptance tests
* Deduplicate the mysql structure file
* Remove custom css class. Use bootstrap classes instead
* Use monolog for logging to the webserver error file
* Use utf8mb4 in fresh MySQL database creation
* Replace uniqid() with random_bytes()

Version 1.8.5
-------------

* Bugfix:

  * Fix issue with SAML2 login for non existing local user

Version 1.8.4
-------------

* Bugfix:

  * Fix password reset

Version 1.8.3
-------------

* Bugfixes:

  * Fix issue when user stays on edit page long enough for the server session to end and data could not be saved

* Enhancements:

  * The tag is saved with onBlur event (because it was not obvious that you had to press enter to save it)
  * The cookies checkbox is now checked by default
  * Add option to specify the full URL of the install to prevent issues with URL guessing on some setups (#567)

* Updates:

  * Update TinyMCE from 4.7.5 to 4.7.9
  * Update jquery-jeditable to 2.0.0

Version 1.8.2
-------------

* Bugfixes:

  * Fig bug where templates from other teams would show up in the Team page

* Updates:

  * Update jQuery, TinyMCE, DropZone and snyk

Version 1.8.1
-------------

* Bugfixes:

  * Fix bad URL generation sent by email after new user registration (#587)
  * Fix problem in API (#569)
  * Fix PHP.ini bad sed (docker only)

* Dev corner:

  * Add Snyk test for vuln detection

Version 1.8.0
-------------

* New features:

  * Add possibility to bulk change visibility for experiments (#527)
  * Add user option to prevent pdf from displaying attached files (#502)
  * Add possibility to add a tag from the API (#468)
  * Add option to disable PDF/A generation and make pdf lighter (no embedded fonts)
  * Add option to change paper format of PDF (A4, Letter, Royal)
  * Add possibility to allow anonymous logins (#279)
  * Add Public visibility to experiments. Will be visible to anonymous users
  * Add possibility to archive a user. The user can then create another account in another team (#483)
  * Add possibility to see and import templates from other members of the team
  * Add button to replace existing uploaded file with new version (#501)

* Enhancements:

  * Add link to revisions from view mode (#536)
  * Add pagination

* Updates:

  * Update Tinymce to 4.7.4
  * Update Fancybox to 3.2.5
  * Update Fullcalendar to 3.7.0
  * Update 3Dmol.js to 1.3.0
  * Update mPDF to version 7.0.2

* Docker:

  * Remove unsafe-inline and unsafe-eval from the Content Security Policy header: now elabftw can be used with a very restrictive CSP header
  * Make the Diffie-Hellman parameters generation in background for faster webserver startup
  * Disable unsafe functions in php.ini
  * Enable open_basedir restriction
  * Use longer SID, store sessions in separate directory with restrictive permissions
  * Disable allow_url_fopen
  * Add config for PHP timezone
  * Add config for setting "set_real_ip_from" in nginx config

* Bugfixes:

  * Fix bug where very long titles without spaces would break the layout (#517)
  * Fix bug where deleting a tag would result in another tag of the same item being deleted (#504)
  * Restrict scheduler slots edit to owner (#506)
  * Fix a display issue with very long titles with no spaces (#517)
  * Fix incorrect redirection in subfolder install (#549)

Version 1.7.8
-------------

* Fix incorrect schema version

Version 1.7.7
-------------

* New feature:

  * Add simple markdown editor (#486) by @Athemis

* Bugfixes:

  * Fix CJK font not displayed inside a table in a pdf (#350)
  * Fix issue in check for update function on sysadmin page behind a proxy (#514) by @zommak
  * Always feed body of experiments to md2html (#510) by @Athemis
  * Fix permission issue on experiments (#498)

* Enhancements:

  * Employ neutral pronouns to refer to the users (#497) by @Armavica
  * Add rel='noopener' to links with _blank target
  * Code cleanup

* Updates:

  * Update Tinymce to 4.7.1
  * Update Dropzone to 5.2.0
  * Update Fullcalendar to 3.6.2
  * Update PHP dependencies

Version 1.7.6
-------------

* Bugfixes:

  * Fix issue with the change-pass page (fix #481)
  * Fix issue with incorrect auth leading to SQL error display

* Updates:

  * Update Tinymce
  * Update Fancybox
  * Update Fullcalendar

Version 1.7.5
-------------

* Bugfixes:

  * Fix bad redirect to install folder for old school install in subfolder of domain
  * Fix issues with the change status/delete menu in show mode
  * Fix issue with body overflowing when you toggle it from show mode (fix #469)
  * Fix bad display of checkbox in show mode
  * Fix issue with get_all functions in API

* Enhancements:

  * Add name of the experimenter on search page (fix #470)
  * Updated composer components
  * Updated tinymce and fullcalendar

Version 1.7.4
-------------

* Bugfixes:

  * Fix issue with checkboxes in show mode in Chrome/Safari (fix #465)
  * Fix issue with delete from checkboxes in show mode (fix #465)

Version 1.7.3
-------------

* Bugfix:

  * Fix issue updating if the database name was different from 'elabftw' (see #462)

Version 1.7.2
-------------

* Bugfix:

  * Fix issue with PHP version 5.6.x (fix #462)

Version 1.7.1
-------------

* Bugfix:

  * Fix issue with not correctly detecting HTTPS behind a proxy

Version 1.7.0
-------------

* Bugfixes:

  * Fix permissions issue on team groups (fix #428)
  * Several minor bugfixes throughout the code were fixed

* New features:

  * Add Steps to experiments (fix #309)
  * Add tags to templates (fix #456)
  * Add a checkbox on items in show mode and a menu to apply an action to several items (fix #427)
  * Add a default Order by and Sort option in profile (fix #370)
  * Add a user preference for generating PDF with CJK fonts (fix #350)
  * Add user pref for single column layout (fix #410)
  * Add possibility to use Markdown in the text editor (fix #302)

* Enhancements:

  * Add the timestamped pdf to the zip archive (see #446)
  * Add an edit button in show mode
  * Check if deleted image is in body. Show warning (fix #432)
  * Submit the select-order-sort on change (fix #451)
  * Better performances in page loading speed
  * Add possibility to change the item type from edit mode
  * Gmagick is now optional. The code will fallback to gd if you don't have gmagick installed
  * Update ChemDoodle to 8.0.0
  * Remove forced capitalization of names (fix #461)

* Internationalization:

  * 100% translated in French
  * New strings need to be translated! See the contributing page to help
* Dev corner:

  * Use Symfony HttpFoundation components (Request/Response/Session/Cookies)
  * Use Guzzle for the requests instead of php-curl
  * Proper documentation of class fields
  * Better use of Twig templates
  * ...and a lot of code moved around, cleaned up, optimized, refactored, obliterated, fixed, ...

Version 1.6.2
-------------

.. warning::

    BREAKING CHANGE for 1.6.x: if you are not using Docker, you'll need to install the gmagick PHP extension!
    You can install it with: pecl install gmagick-2.0.4RC1

* Bugfixes:

  * Fix insert image in text button not working after upload of file (#439)

* Enhancements:

  * Add a way to bind internal (organisation) id to a team (for SAML auth)
  * Add possibility to create an experiment through API (#443)

* Updates:

  * Update php dependencies
  * Update dropzone to 5.1.1
  * Update tinymce to 4.6.4

* Docker:

  * Bring back php-gd because it is needed by mpdf (#438)
  * Remove listen directives for IPv6 in nginx conf (#440)

Version 1.6.1
-------------

.. warning::

    BREAKING CHANGE: if you are not using Docker, you'll need to install the gmagick PHP extension!
    You can install it with: pecl install gmagick-2.0.4RC1

* Bugfixes:

  * Workaround an issue when uploading SVG images containing text (#415) Thanks to @Athemis
  * Fix wrong redirect in to admin panel from sysadmin panel (#404)

* Updates:

  * Update Colorpicker, Fancybox and Tinymce

* Dockerfile:

  * Workaround a bug in Firefox (https://bugzilla.redhat.com/show_bug.cgi?id=1204670): generate random CN for self-signed certificate
  * Add freetype font (for SVG with text)
  * Modify CSP headers to allow blob: fix #406

Version 1.6.0
-------------

.. warning::

    BREAKING CHANGE: if you are not using Docker, you'll need to install the gmagick PHP extension!
    You can install it with: pecl install gmagick-2.0.4RC1

* New features:

  * Add possibility to login through SAML with an Identity Provider (IDP) (fix #47)
  * Add thumbnails for tiff, pdf and svg files (fix #292 #346)

* Bugfixes:

  * Fix a bug where the permissions could not be correctly checked with the API
  * Fix search with multiple tags (thx @oli-ver) (fix #385)
  * Fix a bug where a bogus error message was shown to the user when updating profile (thx @mjeltsch)

* Enhancements:

  * New CSS design allowing more space for content, with a columns layout
  * CSS is now more responsive than ever
  * Status can allow timestamping or not (contribution by @Athemis) (fix #390)
  * Json in zip archive now contains more info (fix #381)
  * Admin can now write to experiments (fix #381)
  * Add image tools to edit an image in the body (fix #228)
  * Better JSON information in zip export (fix #381)
  * Use a temporary path for pdf generation of zip archives (fix #382)
  * Externalisation and minimization of Javascript code
  * Add more supported extensions for 3Dmol.js (fix #398)
  * Add more highlighted languages (fix #398)
  * More pages use templates now
  * Code is getting cleaner and more elegant with each release :)

* Docker image:

  * Add gmagick extension
  * Use PHP's opcache to cache opcode and improve speed

* Dev corner:

  * Use docker for acceptance testing
  * Use yarn instead of bower for JS dependencies

Version 1.5.7
-------------

* Bugfixes:

  * Fix a bug on the link generation of linked items in edit mode of experiments
  * Bring back the show related icon on db items view mode

Version 1.5.6
-------------

* Bugfixes:

  * Fix a bug where the team groups were not showing in the user control panel for default visibility (fix #374)
  * Fix a bug where the star rating were not working
  * Fix the Save button from edit mode

* Enhancements:

  * Update fancybox to latest version (image viewer for attached pictures)
  * Update the JS dependencies to latest version
  * Update the PHP dependencies to latest version

* New feature:

  * Add possibility to add highlighted code (fix #375)

Version 1.5.5
-------------

* Bugfixes:

  * Fix a bug where the number of unvalidated users was not shown in the footer
  * Fix a bug in the admin panel where parts of it were not accessible
  * Fix a bug where the Title would display escaped special characters

Version 1.5.4
-------------

* Bugfixes:

  * Fix a bug limiting uploaded files to 2Mo
  * Fix a bug on Safari where text was not visible in the search bar (contribution from @oli-ver)
  * Fix a bug on Admin panel where you could not resize the template input textarea without messing everything up
  * Fix a bug where the server port was not correctly detected (fix #362)
  * Fix the display of uploaded images as album with Fancybox
  * Fix API key generation when not admin

Version 1.5.3
-------------

* Bugfixes:

  * Fix proper redirection to install page after a fresh install
  * Fix editing templates

Version 1.5.2
-------------

* Bugfixes:

  * Fix bug on search page preventing listing experiments of team users (fix #353)
  * Fix list buttons disappearance on TinyMCE editor (fix #351)

Version 1.5.1
-------------

* Bugfix:

  * Fix bug preventing the use of the todolist

Version 1.5.0
-------------

* New features:

  * Page building time improved greatly thanks to the use of a templating engine
  * Add an API so external programs can interact with eLabFTW (fix #328)
  * Add possibility to order experiments by Comment (fix #320)
  * Add possibility to read the asn1 encoded timestamping token (fix #315)
  * Add possibility to draw something (doodle) (fix #198)
  * Add possibility to filter experiments through visibility (or groups) (fix #335)
  * Add title of experiment/item in the page title (fix #324)
  * Add possibility to select the source of the mention plugin (fix #334)
  * Add possibility to select default visibility for new experiments (fix #312)
  * Add a "Read changelog" button when a new release is available (in Sysadmin panel)
  * Add search with multiple tags (fix #332)

* Bugfixes:

  * Fix an issue where two uploaded files with same name resulted in only one file in a zip archive
  * Fix an issue where you couldn't create a zip/pdf of a list containing an experiment which is not yours

* Enhancements:

  * Use less and better formed SQL queries, making the app 2 times faster
  * Suggest SMTP2GO instead of mailgun for SMTP configuration
  * Send an email to all admins if there are several upon new user registration
  * Uploaded files are now stored in a subfolder of uploads/ (max subfolders: 256)
  * Update composer dependencies to latest version
  * Exported PDF are now in PDF/A format specification (better for long term archiving)

* Docker:

  * Add a custom 404 page introducing Wally the wallaby
  * Unset env var once config.php is written
  * Add API redirect in nginx.conf
  * Merge common parts of nginx.conf
  * Drop SYS_PTRACE capability
  * Set alpine version to 3.5
  * Use libressl instead of openssl
  * Remove sha384sum on composer install
  * Use labels
  * Allow more memory for PHP (fix #333 #347)

* Developer corner:

  * Use Twig as template engine
  * Add canRead and canWrite properties to Entity objects
  * Rename bgcolor to color and drop unused columns
  * Move locale folder inside app/
  * Remove functions.inc.php
  * Remove js/, add compiled files in app/js, rest is in bower_components
  * A lot of class instantiation/usage have been redefined to be more efficient and easy to use
  * Improve code coverage

Version 1.4.3
-------------

* Bugfixes:

  * Use TIMESTAMP instead of DATETIME for Mysql 5.5 users on install, too!

Version 1.4.2
-------------

* Bugfixes:

  * Use TIMESTAMP instead of DATETIME for Mysql 5.5 users

* Enhancements:

  * Better UI for SMTP password field on Sysconfig page

Version 1.4.1
-------------

* Enhancements:

  * The TODOlist is now stored in the MySQL database. Items can be reordered and edited (fix #124)
  * Improve handling of uploaded structure files that are not macromolecules (contribution by @Athemis)
  * Change div overflow from hidden to scroll (fix #314)

* Bugfixes:

  * Update Swiftmailer, fixing a vulnerability related to the php mail() function (https://thehackernews.com/2017/01/phpmailer-swiftmailer-zendmail.html)
  * Update the link for documentation to an external link, now that the documentation is no longer local

Version 1.4.0
-------------

.. warning:: This release contains TWO important changes! Read below.

* **IMPORTANT CHANGE N°1**:

  * The `vendor` directory is not tracked by git anymore. This doesn't impact Docker users BUT THE OTHER POINT BELOW DOES. For git users, you now need to install `composer <https://getcomposer.org>`_. For this update, do like this:

  .. code-block:: bash

      cd /path/to/elabftw
      git pull
      rm -rf vendor # only for this time
      # see https://getcomposer.org to install composer
      composer install --no-dev

  Read the :ref:`new way to update here <how-to-update>`.

* **IMPORTANT CHANGE N°2**:

  * The docker repo changed from elabftw/docker-elabftw to elabftw/elabimg. In order to get the latest version, make sure to edit /etc/elabftw.yml and change the line "image:"; replace "docker-elabftw" with "elabimg".

* New features:

  * Autosave feature when editing an experiment or an item
  * Admin can now see experiments with visibility set to 'only me' (fix #307)

* Enhancements:

  * Improve responsive design for mobile
  * Show installed version even if we can't access latest
  * Show date of latest release in sysadmin panel
  * Allow use of unencrypted SMTP server

* Bugfixes:

  * Redirect to the install folder directly after install if SQL is not imported
  * Allow scrolling of text if it is very wide instead of just hiding it (fix #314)

* Internationalization:

  * Translated to Slovenian at 100% (thanks to Petra Kaferle)
  * Translated to Portuguese (Brazilian) at 100% (thanks to Carlos Kikuti)

* Docker image

  * Repository is now named elabftw/elabimg
  * Some capabilities are dropped
  * Composer is now installed in order to populate the vendor/ dir

* Dev corner:

  * The git repository got ligther. Documentation is now in `elabftw/elabdoc`. API doc is untracked. www.elabftw.net website is no more on the gh-pages branch but on `elabftw/elabweb`. With the removal of the `vendor` dir, this brings the total size of the repo down by about 50%.
  * img/ dir moved to app/

Version 1.3.1
-------------

* Bug fixes:

  * fix bug where admin of a team didn't receive an email whene a new user registered
  * fix bug where scheduler was not working on some browser/operating system combinations

Version 1.3.0
-------------

* New features:

  * add a scheduler to allow booking (bookable) items from the database, on Team page (#238). Head to the admin panel to create a bookable type of item. You can then book it from the Team page.
  * add possibility to show experiments from others from the team. Go to the User Control Panel to set the option.
  * add possibility to send a mass email to all registered users from Sysconfig panel (#271)
  * Chemdoodle: when clicking the Save button on an experiment, the .mol file is automatically uploaded (#174)
  * Sysadmin can now edit users from the Sysadmin panel (#297)

* User interface (contributions by @manonstripes):

  * tooltips appear on icons to display their action
  * better colors for buttons depending on their purpose
  * language select is now displaying language in a user friendly way
  * homogeneization of some pages
  * prettier user interface
  * better user experience

* Bug fixes:

  * fix display of experiments by date (fix #296)
  * fix long lines overflowing on wells
  * fix locked item not editable onclick (thx Arti)
  * fix todolist keyboard shortcut input on user control panel

* Enhancements:

  * password reset link is now only valid for one hour (#297)
  * allow \\ in title and body (#300)

* Internationalization:

  * Catalan is 71% translated
  * Chinese is 68% translated
  * French is 100% translated
  * German is 98% translated
  * Italian is 83% translated
  * Polish is 25% translated
  * Portuguese is 64% translated
  * Portuguese (Brazilian) is 79% translated
  * Russian is 23% translated
  * Slovenian is 91% translated
  * Spanish is 100% translated

  Check the contributing page to help translate.

* Documentation:

  * the documentation has improved a lot
  * Docker install is now default with elabctl
  * add SafeCreative in the timestamping manual (thx @gebauer)

* Dev corner:

  * a whole lot more unit tests
  * code coverage has been enabled
  * acceptance tests are working properly. The config file is swapped for the test DB.
  * files in app/ were deleted and code was moved to classes
  * the inc/ folder is no more! files are in app/
  * updated bower components
  * updated composer components

* Security:

  * activate security switches in php config in docker image
  * add Content-Security-Policy header to docker image
  * add Strict-Transport-Security header to docker image

Version 1.2.6
-------------

* remove the counting of uploaded files (sysconfig page) because it may crash the php process for large number of files

Version 1.2.5
-------------

* fix bug leading to first user in a new team not having correct permissions (was not admin)

Version 1.2.4
-------------

* fix a missing `<div>` element from the sysconfig page preventing correct navigation through tabs

Version 1.2.3
-------------

* fix for MySQL 5.7.5+ (see #273)
* documentation improvements

Version 1.2.2
-------------

* fix a typo preventing users from resetting their password
* prevent duplicate tags from showing (#270)
* improve the install experience of installing in the cloud (use dialog)
* improve the documentation and code syntax

Version 1.2.1
-------------

* update the crypto lib to 2.0

WARNING DOCKER USERS!!!!! IMPORTANT READ BELOW:

Once you pull the new version and visit a page, the config file will be updated with a new secret key. You need to copy it from inside the container to your docker-compose.yml file!

1. Use `docker ps` to check the ID of the container (or use its name)

2. Replace $ID from the below command with your container ID (or name). This command will extract the new key and place it at the end of your config file.

.. code-block:: bash

    docker exec -it $ID grep SECRET /elabftw/config.php| awk -F \' '{print $4}' >> docker-compose.yml

3. Edit `docker-compose.yml` to replace the old SECRET_KEY value by the new one at the end of the file.

Like shown on this image:

.. image:: img/1.2.1.png
    :align: center
    :alt: update config

For normal users (no docker):

If you have a message asking you to make your config file readable, use this: `chmod 777 config.php`. Execute this command from inside the `elabftw` folder.
Refresh the page to retry. You can put back restrictive permissions after the update is done.

This update is a major update from the php-encryption project. So we need to change how the key is. This key is used to encrypt the SMTP and timestamping passwords.

* update a lot of composer components
* update JS components
* fix bug leading to new users being always validated
* add in-depth documentation for docker install

Version 1.2.0-p3
----------------

* fix bug leading to first user on fresh install not being sysadmin + admin

Version 1.2.0-p2
----------------

* fix install
* fix team groups
* remove wrong column in banned_users table
* remove username mention on statistics page

Version 1.2.0-p1
----------------

* fix imported csv without a title
* fix error in php 5.6 preventing sysconfig.php to show up

Version 1.2.0
-------------

* Big changes

  * The username is no more! Login with your email. That happened because:
     * Usernames were not used
     * People tend to forget the username they picked, but always remember their email
     * It simplifies the code by removing clutter

  * Timestamping with openssl has a bug! So we use Java.
     * See `this issue <https://github.com/elabftw/elabftw/issues/242>`_
     * TL;DR It is due to a bug in the OpenSSL library and a change on how the default TSA replies
     * If you install Java you can continue to timestamp
     * If you use Docker, updating the container is enough

* New features

  * Add possibility to promote a user to SysAdmin
  * Add possibility to delete an empty team
  * Add a way to test email configuration directly from config page
  * Add possibility to clear the logs
  * Show usage statistics on sysconfig page
  * Show information about the server on sysconfig page
  * Allow searching for elabid
  * Add buttons to show more or show all items

* Enhancements

  * Improved layout for displaying users, status and items types
  * Improved translation for french, add terms
  * Better notification system
  * Improved "Create new" menus
  * Users using a docker container can now use Let's Encrypt certificates easily
  * Install on a drop is now using a Docker image, and automatic Let's Encrypt certificates

* Documentation

  * Better doc for install on Drop

* Developer corner

  * A lot of things changed under the hood, with the creation of app/models, views and controllers
  * Code moved around to try to have something that looks like an MVC seen from very far away
  * Optimize page load by doing less useless SQL requests
  * Add asynchronous calls everywhere
  * Updated composer components
  * Removed some duplicated code
  * Removed useless code
  * Better CSS code
  * Replace die and exit by Exceptions

Version 1.1.8-p2
----------------

* Bug fixes

  * fix deletion of thumbnails for non jpg images
  * fix name of timestamp pdf
  * fix image display in pdf (fix #234)

Version 1.1.8-p1
----------------

* Bug fixes

  * Fix footer of profile page incorrect

* Documentation

  * Better doc for everything

* Enhancements

  * Remove 'LIMIT 100' on some SQL requests
  * Use download.php to display images. Fix #232

* Developer corner

  * Remove update.php script

Version 1.1.8
-------------

* Bug fixes

  * fix bug where elabid wasn't properly imported from zip archive
  * fix bug in docker where secret_key was absent from config file

* Documentation

  * clarified the Docker installation

* Enhancements

  * improved the docker distribution

Version 1.1.7
-------------

* Bug fixes

  * fix bug where list text size was incorrect (fixed upstream by tinymce devs; #158)
  * fix bug where color of items/status was wrong after editing it
  * fix bug in Docker implementation missing SECRET_KEY value in config file
  * fix bug in SQL syntax of the show action for tags

* Enhancements

  * You can now link experiments directly in text with the `#` autocomplete (fix #191)
  * Search page: when searching for experiments of the whole team, you'll get a list of tags from the whole team
  * Tags autocomplete: now showing completion from the team's tags
  * Molecular structure files (PDB/MOL2/SDF/mmCIF) are previewed using 3Dmol.js (fix #213) Thanks @Athemis.
  * Default hashing algorithm for files changed from md5 to sha256 (thanks @Athemis)
  * Add a pretty loader for autocomplete

* Developer corner

  * use grunt to minify all the JS and CSS files in one
  * updated composer and bower components
  * created the Upload class

Version 1.1.6
-------------

* Bug fixes

    * fix bug on capitalized images extensions (fix #195)
    * fix bug where quotes could break the mention plugin
    * fix bad login url sent to validated users (thx Joke)

* Enhancements

    * Better view on low resolution display (fix #204)
    * Disallow empty title in quicksave
    * add autocomplete to DB items (fix #190)
    * Change new version available banner color
    * Add absract display on mouse hover (fix #196)
    * Add download .asn1 button on timestamped experiments
    * Add autocomplete=off on admin page form
    * Add possibility to have floating images (fix #186)

* Documentation
    * Better manual

* Developer corner
    * use colorpicker instead of colorwheel, remove raphael.js dependence

Version 1.1.5-p2
----------------

* Hotfix: fix bug in permissions on DB items export (zip/pdf) (#183)

Version 1.1.5-p1
----------------

* Hotfix: fix bug in smtp password encryption (#182)

Version 1.1.5
-------------

* Bug fixes

    * fix bug on pdf generation: md5 sum of files not showing
    * fix 'Error getting latest version from server'
    * fix cookies not working properly
    * fix bug related to deletion of files upon user deletion

* New features

    * add user groups (check it out in the admin panel: visibility of experiments can now be set on a group of team members
    * add Remember me button on login page
    * add autocompletion to experiments (write # to get item list) (fix #65)

* Enhancements

    * new registered users will get the server lang as lang
    * tag list on search page is now filtered by selected user
    * improve zip import now also imports attached files to an item (fix #21)
    * add .elabftw.json file in zip archives (to allow easy reimport)
    * remove MANIFEST file from zip archives
    * remove .export.txt file from zip archives

* Documentation

    * move doc to reStructeredText (in doc/_build/html)
    * documentation is hosted at https://elabftw.rtfd.org
    * remove clutter on README.md (and add BADGES!!)

* Developer corner
    * add unit and acceptance tests
    * update composer components
    * use `Defuse/php-encryption <https://github.com/defuse/php-encryption/>`_ for encryption library
    * add API documentation (in doc/api)
    * class Db is a singleton
    * numerous code improvements (see git log)


Version 1.1.4-p3
----------------

* fix bug on install page

Version 1.1.4-p2
----------------

* fix INSTALLED_VERSION constant so it displays correctly if an update is available in sysconfig

Version 1.1.4-p1
----------------
* fix bug in zip/csv generation

Version 1.1.4
---------------

* fix bug in search page showing tags of other teams
* fix bug in search page returning items from other teams
* add ordering options to items types, status and templates (try sorting them!)
* add possibility to export experiments templates to a file (.elabftw.tpl)
* add possibility to import a template from a .elabftw.tpl file
* add possibility to import .elabftw.zip archives in the database
* switch to pki.dfn.de as default timestamper (it is free)
* revamp the timestamping class
* timestamping is properly validated
* add pagebreak tag in editor
* max file upload size is now based on system configuration (thx @jcapellman)
* move creation/duplication functions to Create() class
* timestamped pdf is now in the exported zip along with the .asn1 token
* removed check for update button in footer
* check for latest version on sysconfig page
* various little improvements and bug fixes
* update tinymce to 4.1.10
* update jquery to 2.1.4
* update SwiftMailer to 5.4.1

Version 1.1.3
-------------

* add new way to send emails (thanks to @Athemis)
* add new visibility setting (organization)
* add user guide in doc/ folder
* fix bug on experiment duplication
* display version in sysconfig page
* update pt-BR translation (thanks Kikuti)
* code cleaning

Version 1.1.2-p1
----------------

* fix css layout
* fix german translation (thanks Athemis)
* update JS components (bower update)
* update PHP components (composer update)
* use PSR-4 for autoloading classes

Version 1.1.2
-------------

* add :rfc:`3161` compatible trusted timestamping (#100)
* add filtering options (#15)
* add encryption for passwords of SMTP and Timestamp stored in the SQL database (#129)
* add a check for curl extension at install (#141)
* add hidden field to prevent bot registration (#84)
* fix team_id not added on db tag add
* fix no experiments/db item showing if there is no tags
* update mpdf library
* update swiftmailer library

Version 1.1.1
-------------

* add a CONTRIBUTING file to help contributors
* add tag in search (#63)
* fix a bug where images where not added to timestamp pdf (#131)
* fix a bug in SQL install file (only impacts new installs)

Version 1.1.0
-------------

* multiple file upload now possible
* add ChemDoodle on Team page
* add a bash script in install folder to help beginners
* fix a bug where the top right search bar was not searching at the good place if the lang was not english
* add a log view for the sysadmin
* various little improvements in code
* fix a CSS bug with Chemdoodle
* fix a bug where a file was not properly deleted from system

Version 1.0.0
-------------

* no changes from beta

Version 1.0.0-beta
------------------

* changelog is now in markdown
* move some files in doc/ folder
* improve download.php code
* add deps to composer.json

Version 1.0.0-alpha
-------------------

* different folder structure

Version 0.12.6
--------------

* better docker/haproxy integration
* show counter of unvalidated users to admin

Version 0.12.5
--------------

* add possibility to update via the web

Version 0.12.4
--------------

* add languages: Catalan, Spanish, German and Italian
* easier install on docker
* fix a bug where wrong admin was informed of new user

Version 0.12.0
--------------

* new todolist
* 1 step less for install
* internationalization (only English, Brazilian, Chinese and French at the moment)
* use of gettext for i18n
* the font is now loaded locally
* use bootstrap for css disposition
* fix some issues reported by users
* a lot of other things
* like really a lot of little stuff

Version 0.11.0
--------------

* So many things…

Version 0.10.2
--------------

* Add a possibility for timestamping a pdf export of an experiment
* Removed old update.php content
* Add md5sum to uploaded files
* Display md5sum of attached files in the pdf

Version 0.10.1
--------------

* Fix a bug in authentication
* Error logs make their apparition in the database
* l33t theme is no more
* Removed the github ssl cert (was not used anyway)
* Move files around (js dependencies in js/)
* Better bower integration


Version 0.10.0
--------------

* Support of several teams on the same install
* Fixed a bug in the search page
* Added groups for better permissions control
* Add MANIFEST file in zip archive
* Add lock info in pdf
* Minor bugs fixing and improvements
* A lot of other things

Version 0.9.5
-------------

* Use of bower to keep track of dependencies
* HTML5 video and audio can now be added
* Add a user preference to ask before leaving an edit page
* Add CSV file to ZIP exports
* Add a revision system (to be able to see old versions of an experiment)
* Add body to CSV export

Version 0.9.4.2
---------------

* Add import CSV page
* Add general template for experiments
* Add linked items and comments on PDF
* Easier install on Mac and Windows
* Add linked items list to pdf and list of attached files
* Add links button in editor
* Add image button in editor
* Add URL in CSV export
* Show the lock on database item
* Removed the html from zip export
* Fix div blocks not passing the filter and losing formatting (thx David!)
* Fix a bug with lock/unlock of items
* Fix a bug in zip generation

Version 0.9.4.1
---------------

* Status are now fully editable
* Bugfixes and cosmetic improvements

Version 0.9.4
-------------

* Security improvements against CSRF
* Config is now stored in the database and editable on admin page
* Add detection of login attempts, and configurable ban time and number of tries
* You can only unlock a lock experiment if you are the locker.
* Only a user with locking rights can lock an experiment of someone else.
* You can now forbid users to delete an experiment with a setting in the conf file
* You can add comments on experiments
* Date is now YYYYMMDD
* Email setup is no more mandatory on install
* Updated some js libraries
* Add a 'Saved' notification upon saving with the Save button of TinyMCE
* Clearer code

Version 0.9.3
-------------

* Add item type to folder of zip export
* Add useragent on github API request (checkforupdates)
* Add items locks
* Bugfixes and improvements

Version 0.9.2
-------------

* mpdf replaced html2pdf for pdf creation
* the check for updates button is fixed
* the minimum password size is now 8 characters
* HTTPS is now the only way to use eLabFTW
* install is now easier
* various bugfixes and improvements

Version 0.9.1
-------------

* Possibility to limit the visibility of an experiment to yourself only

Version 0.9
-----------

* Newer versions of JQuery and JQuery UI
* config.ini is now config.php
* Cosmetic changes
* Ctrl-Shift-D will add the date in the editor
* Possibility to search experiments owned by a unique user
* Conformation to coding standard PSR-2

Version 0.8.2
-------------

* Added check for updates button
* TinyMCE 4
* Editor'save button saves date, title and body

Version 0.8.1
-------------

* Admin can reset password
* You can search in everyone's experiments if you want

Version 0.8
-----------

* You can upload big files now
* Better register form
* Fix in html zip export
* Better name of zip files when there is only one experiment
* Bug fixes and improvements

Version 0.7.3.2
---------------

* Apparition of the view arrow to fix the tab opening behavior
* Clicking a tag will now make a search in the tags only
* No more root user, admin user is made on install
* Force https
* Fix bugs
* Upgrade the mail library (swift)
* Documentation for backup

Version 0.7
-----------

* Multiple bugfixes
* Real search page
* Possibility to export in zip or spreadsheet
* Thumbnails are clickable
* Better pdf generation
* Better html generation
* Install is now easier

Version 0.6
-----------

* Switch repo from gitorious to github (because it has wiki, bug tracker, and bigger community)
* Items in DB can now be everything, and you can edit them
* Improvement on reset password strategy
* eLabID is a unique ID bound to each experiment (useful for tracking raw data)
* Star ratings are shown on DB show mode
* You can lock for edition an experiment
* Autosave every second on edit
* Improvements in .zip creation
* Multiple bugfixes
* Show linked experiments to a database item

Version 0.5.8 and 0.5.9
-----------------------

* I don't really care about version numbers, I do it for fun.

Version 0.5.7
-------------

* Database
* Publish button
* TinyMCE for editing the body (text formatting)
* Better info boxes
* Better presentation of UCP
* Better search

Version 0.5.6
-------------

* Various bugfixes

Version 0.5.5
-------------

* Calendar on date
* Autocomplete on tags
* Ajax for tags

Version 0.5.4
-------------

* Added modification «history» on protocols
* Added dates on labmeeting and journal clubs uploads

Version 0.5.3
-------------

* Added templates for experiments
* You can now upload past journal clubs, labmeetings
* Added robots.txt file

Version 0.5.2
-------------

* TODO list accessible via a keyboard shortcut ('t' by default)
* Better profile
* Better TEAM page

Version 0.5.1
-------------
* No more Scriptaculous/Prototype, only jQuery
* TODO list added
* Images are now in themes folders
* Various FTW titles
* Git repo @ gitorious

Version 0.5
-----------

* UCP
* Themes
* Keyboard Shortcuts
* View modes
* Admin Panel
* Profile
* Send zip by email
* Better Tagcloud
* Can attach protocol to experiment
* User need validation after registration
* Unique config.ini file

Version 0.4
-----------

* Tagcloud
* Recover password
* Make zip archive
* Editable file comments

Version 0.3
-----------

* Tags on a separate table
* Make pdf
* Statistics
* Comment on attached files
* Quick tagsearch

Version 0.2
-----------

* Search page
* Password storage using salted SHA-512
* Attaching files

Version 0.1
-----------

* Register / Login
* Show / view / edit / duplicate :: experiments / protocols
