#Concept note - detail 
Note: pls see the accompanying ppt first

##Most basic requirement
We need a website that opens up a PDF into its individual pages, and lets people post their comments for every page.
(If you know such a website then please tell me!)

##Document's own “profile” page
1.	This would display a description, and properties like upload date, bookmarks list, etc. 
2.	Users can download a copy of the PDF here.
3.	It would also have its own comments feed (separate from that of the individual pages), where larger issues pertaining to the thing as a whole can be brought up and discussed.
4.	There would be an activity stream here showing a listing of the recent comments posted in its pages... clicking on them would take us to the page, and highlight the placemark if present.
5.	Statistics displayed : Ranking of pages by comments / placemarks / various types of comments. So readers can find and jump to the most-commented page etc.
6.	Options to export and save all the commenting etc done on this doc would be available here, for all visitors.
7.	There would be a huge button of course inviting users to open the doc and go to page 1.
8.	On the DB side, can set the comments collecting here to be for page 0.

##Rendering
1.	Internally we might have to render the PDF's pages as images. Thats ok; we can use tools like pdftoppm. (command : pdftoppm -png [filename].pdf [prefix]  )
2.	We don't need to extract content from the PDF : in most cases anyways, we can't! We just need to be able to display the page exactly as it’s printed, and then be able to comment on that.

##Adjoining pages
1.	Feature: When viewing one page. User can check-on an option to load the next page on the side. This is for cases where content like a table is spread out across two pages and both the pages need to be viewed together.
2.	No need to disable commenting etc for the second of a two-page table layout.  Let users automatically gravitate to the first of the pair.
3.	Permit out-of-bounds marking (like, 150%) on width(x) side, as the placemark might be made on an adjoining page which might be a spread-out table or so; we want the discussion to still happen on the initial page.
4.	Keep a setting for documents that are right-to-left reading, and if so, load the adjoining page on left side instead of right.
5.	Owner can set which pages should load adjoining page by default.
6.	Can keep an automation: If a placemark was posted at a position of x above 100 or below 0, then the system loads the adjoining page by default. Else, after say, 10 comments have been posted, if majority commenters opted to load adjoining page, then make it default.

##Commenting
1.	Keep a character limit of around 500, give option to give link for expanded explanation, link them to pastebin.com etc. We don’t want overly long comments here droning on and on; users should be encouraged split them into neat points and categorized them properly.
2.	Comments are categorized as : QnA, Suggestion, Criticism, Compliment, Other. Why : to cleanly segregate them. So that we see the criticisms only when we want to; not while one is looking for suggestions. So the people asking genuine questions can get genuine replies and not rhetorics or sarcasm. If someone wants to post additional info that would inform the discussion then that comes under QnA.

##Bookmarks / Chapters
1.	Can try out nesting of some bookmarks under others to show hierarchy, but really with a document published linearly, a flat linear set of bookmarks will do. The uploader can always just rename a sub-section to show hierarchy, like giving "--" prefix or so.
2.	Facility for users to suggest a bookmark/chapter name for the current page they’re seeing. The proposed name gets taken, in a small popup textbox and sent to the owner.

##Placemarks
1.	It would be wonderful to have this, as annotating feature.
2.	It would have a short title followed by a comment-long text. The title is for displaying when user hovers their mouse over the placemark.
3.	Editing a placemark : Forget it. Just delete that comment and add another one at the right place.
4.	How to store the placemark’s position : x, y distance from one corner (probably top left) stored as a % of total height and width of page (image) : this way it retains the correct position when the page is zoomed in or out. Round off to some decimal places which gives a fairly accurate marking.
5.	Keep a degree of sameness, by which if a new placemark is too close to an existing one, then the user is redirected to the existing placemark. This could happen at the right-click stage itself: right-clicking near an existing placemark would give an alternate context menu with “go to this comment”.

##Trusteeship for important documents
Users could voluntarily submit documents to the admin's trusteeship and not keep them under their control. In initial phases, all documents would be hosted by the website admin anyway.
What if a seemingly important document with a good amount of ongoing activity

##Users uploading their own documents
1.	Initially, the site would feature its own set of documents, open for collaborative commenting by users who register using their email id’s (typical signup-membership).
2.	There would be an invitation to users to email in documents that they want hosted, along with reasoning to establish importance.
3.	Subsequently, the platform would automate this and make it possible for registered users to upload their own documents.
4.	The website would retain a “featured” listing of documents on its homepage, followed by listing docs uploaded by users.

##Group Collaboration
1.	Users form groups and collaboratively annotate a document, and so we could see documents being annotated by limited groups and not anyone & everyone.
2.	If there is a document already published and being publicly annotated, then a group can create a fresh for-the-group copy of it, for starting afresh. They would be given the option to choose whether to import existing comments or not. The document profile would then link to group-annotated versions of itself.
3.	For example, an advocacy group could show off its group members’ detailed opinions about a proposed law amendment. Another group could present their version as well.
4.	In this, I would insist that the visibility, if not the commenting ability, of each document should remain public. Since this tool would be released open-source, private groups can do things privately on their own server.

##Import and Export data
1.	On the document’s properties (or “profile”) page, there would be an option to download all the commentings done so far in an XML. 
2.	Having placemark data if any. 
3.	Referenced by page number.
4.	The download option would be available publicly.
5.	This same data can then be uploaded to another document profile, even on another server. This way, one can “migrate” a document along with all the annotations made to another platform, or backup.
6.	In case the new doc doesn’t have as many pages as the previous one, the excess comments would be put in another XML and given for download.
7.	Other independently developed tools can take this XML data and make published / formatted / simple text versions of it.

##Sharing
1.	Every page has its own URL.
2.	Every comment has a permalink. If it is attached to a placemark, then the page with just this marked spot is displayed at the top, then the comment stream below it. There is a link to the page’s URL given which will take the reader to the full
3.	Conventional URL-shorteners can be integrated to make sharing easier

##Licensing
1.	I’m quite sure such tools already exist in the private/commercial domain. No point in re-inventing for that.
2.	It’s the open-source / free portal domain where I’m yet not able to find any tool that meets this simple requirement. 
3.	Hence, this work is licensed under a Creative Commons Attribution-NonCommercial 4.0 International License. See http://creativecommons.org/licenses/by-nc/4.0/ for details.
4.	Only restriction: derivatives of this shouldn’t get used for commercial purposes, for the simple reason that that field is already well covered.
5.	But I’m considering going for a more open license like Free Culture or MIT Free Software license.
