WP Help Pointers
================

Class for registering and using custom WP Help Tooltips in WP 3.3+

How to Use:
===========
  In your functions.php file:
  		require_once('class.wp-help-pointers.php');


  Pointers are defined in an associative array and passed to the class upon instantiation.
  This is done by hooking into 'admin_enqueue_scripts'
 
 		add_action('admin_enqueue_scripts', 'myHelpPointers');
 		function myHelpPointers() {
 		   //First we define our pointers 
 		   $pointers = array(
 		                    array(
 		                        'id' => 'xyz123',   // unique id for this pointer
 		                        'screen' => 'page', // this is the page hook we want our pointer to show on
 		                        'target' => '#element-selector', // the css selector for the pointer to be tied to, best to use ID's
 		                        'title' => 'My ToolTip',
 		                        'content' => 'My tooltips Description',
 		                        'position' => array( 
 		                                           'edge' => 'top', //top, bottom, left, right
 		                                           'align' => 'middle' //top, bottom, left, right, middle
 		                                           )
 		                        )
 		                     // more as needed
 		                     );
 		   //Now we instantiate the class and pass our pointer array to the constructor 
 		   $myPointers = new WP_Help_Pointer($pointers);

