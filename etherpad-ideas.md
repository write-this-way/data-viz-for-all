Data Viz for All: Help Us Make Interactives More Usable for Mobile

https://etherpad.mozilla.org/srccon2015-mobile-dataviz

Aaron Williams (@aboutaaron)
Julia Smith (@julia67)
Youyou Zhou (@zhoyoyo)

GitHub: https://github.com/julia67/data-viz-for-all

Problems:
 * Size of data - The large datasets you can visualize on a desktop don't always translate to mobile
 * Hovering / hover states
 * Mobile browser / network speeds and slowness
 * JavaScript dependencies i.e., forcing users to download multiple, unminified libraries
 * Maintaining scroll position
 * Embedded content on third-party CMSes and partner sites
 * Font legibility
 * Designing for very small screen sizes
 * Tooltips and positioning
 * Correct sizes for buttons and other UI elements
 * Dealing with viewport height
 * Handling content when rendered on non-responsive, mobile-specific sites, e.g., content on m.yournewsroom.com
 * Handling events and sizing for checkboxes and filters
 * Sticky / fixed elements
 * Social media sharing to apps on device e.g., Twitter links opening up in the phone's Twitter app
 * Audio and video
 * Handling rotation / screen orientation
 * Mobile plan data limits 
 * Accessibility for users with sight and motor disabilities
 * Z-INDEX (or the 'zed'-index)

Pick your table!

Group A -- tooltips/hovering
-On mobile--fixed area for the information
-Navbar/dropdown where you can select the data but still see the viz
-Modal 
-Modal that functions like a Lightbox where you sequentially go through the data
-Or cards that fill up the whole viewport --SWIPE! 
-Chunking to avoid tooltips altogether
-Target people's natural behaviors (swipe/scroll vs tapping and zooming)
-stepping reader through data vs having people discover it for themselves

Group D question for A: How to stop page scroll while the modal is open (example http://apps.wbur.org/books/)
Set overflow:hidden; on the body
Ha, I had body.model-open{ overflow: visible; } by mistake. Thanks

Google Material Design Cards: http://www.google.com/design/spec/components/cards.html

Group B (the Fighting Mongooses)

Topic: How do you react to the device/environment/screen

 * Breakpoints: where to have them
   * Wordpress black bar
   * Pre-determined breakpoints can be a pain
 * Testing
   * Android mostly
   * Windows phone: no
   * Browserstack
 * "Retina" display
   * Better legibility
   * More things to think about
 * Responsive images
   * Smaller images
   * Different sizes
   * Media query to show different images.  Display: none still load images
   * Foundation CSS has a tool to create different size JS
     * +++ on Foundation
     * 17 column grid
 * Modernizr, detecting features
   * Touch screen is harder now
   * Detect feature not by device/browesr detection
 * Mobile first
   * It's ok to give IE8 a mobile version
 * SASS/LESS makes it really easy to keep media queries styles with their actual
   * Pleeease puts media queries together
   * PostCSS
 * Information design
   * Hard to determine what to show or not show
   * Mobile first is good but need to think about it separately
   * When is the piece going to be used (at home or on the go)
   * User testing to show that some things were not missed on mobile
   * Sometimes its hard to deal with taking things away when there is lots of investment
   * It's less space, deal with it
 * Tablets
   * Don't check enough
 * Hire people that have devices and use them often
 * It's nice to get a set of devices
   * Hard to get and deal with expensing
   * iPad needs executive approval
 * Interactives are hard to show up in (native) apps or mobile only site
 * Screen readers on mobile devices
 * Apple Watch :(
 * Text is important


Group C

Topics: maps

 * Can we split the map into regions? (Northeast, Mid-Atlantic, etc.)
 * Don't force interaction, fall back to text+image/animated-gifs if we need to.
 * Think about mobile early (even in editorial decisions?)

Group D: Line charts
    Problems:
        Landscape orientation
        Multiple series
        Labels
        Overall trend vs. maintaining same level of detail
    
    Solutions:
        Simplified initial view (e.g. fewer y-axis ticks) to show trend, but tap for more details
        Details mode: Sideways scrollable or tap to drill in (http://square.github.io/crossfilter/)
            How to indicate that you should scroll?
                Use copy/helper text to provide context
        Table below chart for details
        For tooltip-like data, drag along the line rather than tap on specific points
        Fixed info area for specific point values
            Show all series simultaneously (A dynamic legend?)
            Needs to show the points and indicate which ones will be in the chart
        Google Analytics (native iOS version) already solved a lot of this


Group E

Group F: US maps
 * some maps (like state maps) can be solved with block cartograms, but that doesn't work for more detailed maps (maybe county-level maps)
 * may be effective to marry the map with a table or some other way to show data (did this in the past: http://commonhealth.wbur.org/2014/01/interactive-childbirth-massachusetts-hospitals)
 * for SVG maps (d3, etc.) performance is an issue on mobile for more detailed maps
 * consider taking the mobile user through important slices and interactions in a static version on mobile that would be more open-ended on the more interactive desktop version (http://www.nytimes.com/interactive/2014/09/19/nyregion/stop-and-frisk-is-all-but-gone-from-new-york.html)
 * take the interactive controls from the map and take them outside the visualization
 * where possible, use native controls (text inputs, form controls, search boxes)
 * if possible, localize to simplify (this could even be done with geolocation of some kind)
 * don't be afraid of images (http://www.nytimes.com/interactive/2015/05/03/upshot/the-best-and-worst-places-to-grow-up-how-your-area-compares.html?_r=0&abt=0002&abg=1)
