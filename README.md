# utl-never-lose-your-program-poor-mans-version-control-using-the-classic-l980s-sas-editor
Never lose your program poor mans version control using the classic l980s sas editor 
    %let pgm=utl-never-lose-your-program-poor-mans-version-control-using-the-classic-l980s-sas-editor;

    Never lose your program poor mans version control using the classic l980s sas editor

    github
    http://tinyurl.com/548pennz
    https://github.com/rogerjdeangelis/utl-never-lose-your-program-poor-mans-version-control-using-the-classic-l980s-sas-editor

    Related repos on end

    Best in 1980s classical editor

    Never lose your sas program.

     Every 60 seconds a timestamped version of the code you are working on is save in folder c:/ver
     with the name pgm.sas

     Every time you save your program in c;/utl (arbitrary folder), a time stamped version is save
     in c:/ver

     If you are working on utl_getxls32983.sas

     1. every 60 seconds utl_getxls32983.sas is saved/overwritten in c:/ver/pgm.sas
     2, if you save the program in c:/utl a timestammed version is save in

        d:/ver/

     Where     name                 data modified
               ====                 =============

     d:/ver/   pgm.sas              6/13/2017 4:24  * save/overwritten every 60 seconds

     d:/utl/   utl_getxls.sas       6/13/2017       * save/overwritten when you save
     d:/ver/   utl_getxls32984.sas  6/13/2017 4:25  * a timestamped copy is automatically save (without any addition keystrok)


    see
    https://goo.gl/5aMfok
    https://communities.sas.com/t5/SAS-Enterprise-Guide/How-to-effectively-manage-version-control-on-SAS-EG-UNIX/m-p/366690

    Versioning your classic SAS programs

    Set autosave to every minute saving intto d:/ver/pgm.sas

    HAVE (program in old text editor)
    =================================

    COMMAND ===>

    000001 %let pgm=utl_getxls;
    000002
    000003 libname sd1 "d:/sd1";
    000004 data sd1.class;
    000005   set class;
    000006 run;quit;
    000007 libname sd1 clear;
    000008

    WANT (timestamped versions of the program saved in d:/ver and c:/ver (without timestamp)
    ========================================================================================


     Where     name                 data modified
               ====                 =============

     d:/ver/   pgm.sas              6/13/2017 4:26  * save/overwritten every 60 seconds

     d:/utl/   utl_getxls.sas       6/13/2017       * save/overwritten when you save
     d:/ver/   utl_getxls32984.sas  6/13/2017 4:25  * a timestamped copy is automatically save (without any addition keystrok)



       1. Put this line in your autoexec
          %Let _q=%sysfunc(int(%sysfunc(time())));
       2. The first line of your program should be
          %let pgm=utl_getxls;
          Execute the let statement at least once (one hand highlight and RMB submit)
       3. Put this on function key F1
          file &pgm..sas;file "d:\ver\&pgm.&_q";%let _q=%eval(0&_q.+1);


           KEY        LEN    VAL

           F1          71    pgm;file &pgm..sas;file d:\ver\&pgm.&_q..sas;%let _q=%eval(0&_q +1);

           I map F1 to the middle mouse button on the Logitech MX310 mouse


    for my performance command macros
    https://www.dropbox.com/s/pwx0r8dqko1ocoj/utl_perpac.sas?dl=0


       1. Create a folder on your h drive called h:/ver
       2. Put this line in your autoexec  '%Let _q=%sysfunc(int(%sysfunc(time())));' make sure _q is global
       3. You need to set up a macro variable pgm that contains the program name your are working on.
          (I use a command macro xinc to set the program macro variable. I type 'xinc myprogram'  to bring
          a program into display manager - and set bunch of other macro variables ie full path and set PWD in unix)
          Alternately, you can put this line, '%let pgm=myprogram;', after the '%inc init.sas' and
          execute the line to set the pgm variable
          I can highlight the line and hit right mouse button and the macro pgm is avaliable to windows.
       4. put this on a function key F11 (you have to be in your program directory in windows)
          pgm;file &pgm..sas;file "h:\ver\&pgm.&_q..sas";%let _q=%eval(0&_q.+1);
       5  each time you press F11 your program will be timestamped and save in H;\ver\myprogram11897.sas
       6 as a side note using the option -autosaveloc  h:\ver on you sas invocation icon will save pgm.asv
         in h:\ver

       Review documentation
       1. Put this line in your autoexec
          The numer of seconds into the day goes int macro var _q
          %global _q;
          %Let _q=%sysfunc(int(%sysfunc(time())));
       2. The first line of your pprogram should be
          %let Pgm=Fab_Dem;
          Execute this at least once
       3. Put this on the shift right mouse button
          file &pgm..sas;file "c:\ver\&pgm.&_q";%let _q=%eval(0&_q.+1);

    /*        _       _           _
     _ __ ___| | __ _| |_ ___  __| |  _ __ ___ _ __   ___  ___
    | `__/ _ \ |/ _` | __/ _ \/ _` | | `__/ _ \ `_ \ / _ \/ __|
    | | |  __/ | (_| | ||  __/ (_| | | | |  __/ |_) | (_) \__ \
    |_|  \___|_|\__,_|\__\___|\__,_| |_|  \___| .__/ \___/|___/
                                              |_|
    */

    https://github.com/rogerjdeangelis/Creating-command-macros-for-the_1980s-DMS-Classic-Editor
    https://github.com/rogerjdeangelis/utl-another-classic-long-to-wide-transpose-using-Arts-untanspose-macro
    https://github.com/rogerjdeangelis/utl-are-classic-editor-command-macros-fsview-and-fsedit-more-useful-than-viewtable
    https://github.com/rogerjdeangelis/utl-classic-editor-comment-out-a-block-of-text
    https://github.com/rogerjdeangelis/utl-classic-editor-commnand-macro-to-repair-sas-satement-with-uunbalanced-quotes
    https://github.com/rogerjdeangelis/utl-classic-problem-transposing-multiple-pairs-of-variables
    https://github.com/rogerjdeangelis/utl-classic-problem-with-proc-transpose-and-mutiple-variables-seven-solutions
    https://github.com/rogerjdeangelis/utl-classic-sas-and-well-designed-tables-and-ascii-graphics-instead-of-bling
    https://github.com/rogerjdeangelis/utl-classic-transpose-by-index-variableid-and-value-in-sas-r-and-python
    https://github.com/rogerjdeangelis/utl-classic-untranspose-problem-posted-in-stackoverflow-r
    https://github.com/rogerjdeangelis/utl-comment-out-a-block-og-code-in-the-classic-1980s-dms-editor
    https://github.com/rogerjdeangelis/utl-how-to-set-up-the-classic-1980s-classic-editor
    https://github.com/rogerjdeangelis/utl-interactive-processing-using-classic-SAS-prompt-user-for-input
    https://github.com/rogerjdeangelis/utl-latest-command-macros-for-the-sas-classic-editor
    https://github.com/rogerjdeangelis/utl-location-of-program-folder-and-classic-editor-program-versioning
    https://github.com/rogerjdeangelis/utl-reading-a-classic-text-file-with-header-and-mutiple-trailers
    https://github.com/rogerjdeangelis/utl-sas-classic-editor-function-keys-for-comments
    https://github.com/rogerjdeangelis/utl-sas-scripting-commands-only-available-in-the_1980s-classic-editor
    https://github.com/rogerjdeangelis/utl-setting-your-classic-editor-dms-function-keys-mouse-actions-and-command-line
    https://github.com/rogerjdeangelis/utl-simple-classic-transpose-pivot-wider-in-native-and-sql-wps-r-python
    https://github.com/rogerjdeangelis/utl-spell-check-words-in-any-classic-editor-window-ie-pgm-note-log-output
    https://github.com/rogerjdeangelis/utl-trimming-padded-lines-in-the-classic-editor
    https://github.com/rogerjdeangelis/utl-using-classic-sas-and-proc-fslist-to-view-a-file-in-hex
    https://github.com/rogerjdeangelis/utl_classic_editor_command_macro_performance_package
    https://github.com/rogerjdeangelis/utl_classic_editor_hilite_and_evaluate_math_functions
    https://github.com/rogerjdeangelis/utl_classic_editor_keyboard_macros_and_abbreviations
    https://github.com/rogerjdeangelis/utl_classic_editor_part_II
    https://github.com/rogerjdeangelis/utl_classic_editor_pfkeys_prefix_mouse
    https://github.com/rogerjdeangelis/utl_classic_editor_place_comment_box_at_cursor_location_with_single_keystroke
    https://github.com/rogerjdeangelis/utl_classic_editor_programatic_cursor_positioning_with_store_cut_and_paste
    https://github.com/rogerjdeangelis/utl_classic_editor_seemless_connection_workstation_unix_server
    https://github.com/rogerjdeangelis/utl_classic_editor_using_a_prefix_mask_to_facilitate_fixed_column_data_entry
    https://github.com/rogerjdeangelis/utl_classic_sas_can_identify_xls_and_xlsx_even_if_the_extension_disagrees_with_the_format
    https://github.com/rogerjdeangelis/utl_classic_sas_editor_display_manager_commands_improved
    https://github.com/rogerjdeangelis/utl_classic_sas_graph_greplay_harvard_macro_multiple_plots_per_page
    https://github.com/rogerjdeangelis/utl_classic_sas_graph_three_plots_across_many_methods_long_live
    https://github.com/rogerjdeangelis/utl_classic_transpose_in_r_and_sas
    https://github.com/rogerjdeangelis/utl_create_your_own_dashboard_using_classic_base_sas
    https://github.com/rogerjdeangelis/utl_data_entry_and_edit_of_tables_in_classic_sas_fsedit
    https://github.com/rogerjdeangelis/utl_javascript_and_classic_map_graphics_with_mouseovers_and_multiple_drilldowns
    https://github.com/rogerjdeangelis/utl_performance_package_SAS_classic_editor
    https://github.com/rogerjdeangelis/utl_proc_gmap_classic_graphics_grid_containing_four_states
    https://github.com/rogerjdeangelis/utl_sas-classic-editor-point-and-shoot-a-proc-freq
    https://github.com/rogerjdeangelis/utl_sas_classic_editor
    https://github.com/rogerjdeangelis/utl_sas_classic_graphics_15_plots_on_a_page
    https://github.com/rogerjdeangelis/utl_sas_classic_graphics_designing_your_greplay_template
    https://github.com/rogerjdeangelis/utl_sas_classic_graphics_grid_of__proc_univariate_histograms
    https://github.com/rogerjdeangelis/utl_sas_classic_graphs_using_phil_mason_grid_macro_for_layout
    https://github.com/rogerjdeangelis/utl_soapbox_001_classic_sas_and_the_programmer
    https://github.com/rogerjdeangelis/utl_where_is_waldo_classic_computer_vision
    https://github.com/rogerjdeangelis/utl_wps_sas_classic_graphics_optimum_minimums_maximums_increments_for-axes
