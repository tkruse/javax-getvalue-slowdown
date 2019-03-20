# javax el getValue( )slowdown

Experimental project to reproduce a performance degradation in javax el.


    org.apache.tomcat:tomcat-jasper-el:7.0.8
    300000 expressions in 85 ms (average 2.8333333333333335E-4 ms/expression)

    org.mortbay.jasper:apache-el:8.0.33
    300000 expressions in 208 ms (average 6.933333333333333E-4 ms/expression)
    
    