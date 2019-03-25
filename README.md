# javax el getValue( )slowdown

Experimental project to reproduce a performance degradation in javax el.


    org.apache.tomcat:tomcat-jasper-el:7.0.8
    300000 expressions in 85 ms (average 2.8333333333333335E-4 ms/expression)
    ... and repeated runs around 100ms


    org.apache.tomcat:tomcat-jasper-el:8.5.39
    300000 expressions in 208 ms (average 6.933333333333333E-4 ms/expression)
    ... and repeated runs around 200ms
    
One important factor for the difference seems to be seemingly unnecessary indirection in the new

    ELContext.java:
    public Object convertToType(Object obj, Class<?> type) {
        ...
    }

When obj is assignable from type, eg.

    convertToType("Hello", String.class);
    convertToType(foo, Object.class);
