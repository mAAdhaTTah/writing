---
ID: 3158
post_title: tinyce-plugin.php
author: James DiGioia
post_date: 2015-02-14 18:37:09
post_excerpt: ""
layout: gistpen
permalink: >
  http://jamesdigioia.com/gistpens/tinymce-button-plugin/tinyce-plugin-php/
published: true
---
( function() { // Register plugin tinymce.create( 'tinymce.plugins.plugin_slug', { init: function( editor, url ) { // Add the Insert Gistpen button editor.addButton( 'plugin_slug', { //text: 'Insert Shortcode', icon: 'icons dashicons-icon', tooltip: 'Insert Shortcode', cmd: 'plugin_command' }); // Called when we click the Insert Gistpen button editor.addCommand( 'plugin_command', function() { // Calls the pop-up modal editor.windowManager.open({ // Modal settings title: 'Insert Shortcode', width: jQuery( window ).width() * 0.7, // minus head and foot of dialog box height: (jQuery( window ).height() - 36 - 50) * 0.7, inline: 1, id: 'plugin-slug-insert-dialog', buttons: [{ text: 'Insert', id: 'plugin-slug-button-insert', class: 'insert', onclick: function( e ) { insertShortcode(); }, }, { text: 'Cancel', id: 'plugin-slug-button-cancel', onclick: 'close' }], }); appendInsertDialog(); }); } }); tinymce.PluginManager.add( 'plugin_slug', tinymce.plugins.plugin_slug ); function appendInsertDialog () { var dialogBody = jQuery( '#plugin-slug-insert-dialog-body' ).append( '[Loading element like span.spinner]' ); // Get the form template from WordPress jQuery.post( ajaxurl, { action: 'plugin_slug_insert_dialog' }, function( response ) { template = response; dialogBody.children( '.loading' ).remove(); dialogBody.append( template ); jQuery( '.spinner' ).hide(); }); } })();