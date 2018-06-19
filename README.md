# utl_sas_classic_graphics_grid_of__proc_univariate_histograms
SAS classic graphics grid of proc univariate histograms. Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.
    SAS classic graphics grid of proc univariate histograms

    see graph
    https://tinyurl.com/ycbqcbhq
    https://github.com/rogerjdeangelis/utl_sas_classic_graphics_grid_of__proc_univariate_histograms/blob/master/utl_sas_classic_graphics_grid_of__proc_univariate_histograms

    see
    https://tinyurl.com/yce8rcrf
    https://github.com/rogerjdeangelis/utl_sas_classic_graphics_grid_of__proc_univariate_histograms

    INPUT
    =====

     SASHELP.CLASS T otal obs=19

       NAME       SEX    AGE    HEIGHT    WEIGHT

       Alfred      M      14     69.0      112.5
       Alice       F      13     56.5       84.0
       Barbara     F      13     65.3       98.0
      ....

    EXAMPLE OUTPUT
    ==============


    +-----------------------------------------------------------+
    |                                                           |
    |  +------------+                                           |
    |  |  N      19 |                                           |
    |  |  MEAN   60 |                                           |
    |  |  MEDIAN 63 |                                           |
    |  +------------+                                           |
    |                                                           |
    |  6 +            *****      *****                          |
    |    |            *****      *****                          |
    |  5 +            *****      *****      *****               |
    |    |            *****      *****      *****               |
    |  4 +            *****      *****      *****               |
    |    |            *****      *****      *****               |
    |  3 +            *****      *****      *****               |
    |    |            *****      *****      *****               |
    |  2 +            *****      *****      *****               |
    |    |            *****      *****      *****               |
    |  1 + *****      *****      *****      *****      *****    |
    |    | *****      *****      *****      *****      *****    |
    |    -----------------------------------------------------  |
    |       52.5       57.5       62.5       67.5       72.5    |
    |                                                           |
    |                       HEIGHT Midpoint                     |
    |                                                           |
    |  +------------+                                           |
    |  |  N      19 |                                           |
    |  |  MEAN   82 |                                           |
    |  |  MEDIAN 95 |                                           |
    |  +------------+                                           |
    |                                                           |
    |  7 +                   *****                              |
    |    |                   *****                              |
    |  6 +                   *****    *****                     |
    |    |                   *****    *****                     |
    |  5 +                   *****    *****                     |
    |    |                   *****    *****                     |
    |  4 +                   *****    *****                     |
    |    |                   *****    *****                     |
    |  3 +                   *****    *****                     |
    |    |                   *****    *****                     |
    |  2 +                   *****    *****    *****            |
    |    |                   *****    *****    *****            |
    |  1 + *****    *****    *****    *****    *****    *****   |
    |    | *****    *****    *****    *****    *****    *****   |
    |    -----------------------------------------------------  |
    |         50       70       90      110      130      150   |
    |                                                           |
    |                       WEIGHT Midpoint                     |
    |                                                           |
    +-----------------------------------------------------------+



    PROCESS
    =======

    * It is my belief that univariate historgram plots work
    much better with goptions then ods. 'Histogram" option is one of the classic
    options. I neve could get inheight and height to work with
    ods graphics. Note you can use ODS graphics and unpack the plot but I
    don't think it i  as flexible, non-programmer approach?


    %utlfkil(d:/png/&pgm..png); * better to delete it before hand;

    filename outfile "d:/png/&pgm..png";
    run;quit;
    goptions reset=all gsfmode = replace gsfname = outfile  device=png htext=2;
    proc univariate data=sashelp.class;
        label weight="Weight Histogram";
        class sex;
        var weight;
        histogram weight   / inheight=3 nrows=2 ncols=1
        ;
        inset  N  Std  q1="25%" median q3='75%'
            / pos    = nw
            format = 3.
            height=3
        ;
    run;quit;
    filename outfile clear;
    run;quit;



    OUTPUT
    ======

    *                _              _       _
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|

    ;

      * just use sashelp.class;

    *          _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| '_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    ;

