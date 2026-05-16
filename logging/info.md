1) Logger objects are organized in a hierarchical namespace and child Logger objects may inherit some logging properties from their parents in the namespace. <br>
2) These Logger objects allocate LogRecord objects which are passed to Handler objects for publication. Both Logger and Handler objects may use logging Level objects and (optionally) Filter objects to decide if they are interested in a particular LogRecord object. When it is necessary to publish a LogRecord object externally, a Handler object can (optionally) use a Formatter object to localize and format the message before publishing it to an I/O stream. <br>
3) Please check the below strucutured flow. <br> Filter, Formater, Handler can be one or more in this flow as per the need. <br>
 Please refer ![Log flow Screenshot](resources/logging-flow.png) <br>
4) Handlers <br>
  Java SE provides the following Handler classes: <br>
    a) StreamHandler: A simple handler for writing formatted records to an OutputStream. <br>
    b) ConsoleHandler: A simple handler for writing formatted records to System.err. <br>
    c) FileHandler: A handler that writes formatted log records either to a single file, or to a set of rotating log files. <br>
    d) SocketHandler: A handler that writes formatted log records to remote TCP ports. <br>
    e) MemoryHandler: A handler that buffers log records in memory. <br>
5) Default Configuration <br>
    The default logging configuration that ships with the JDK is only a default and can be overridden by ISVs, system administrators, and end users. This file is located at java-home/conf/logging.properties.<br>
6) Unique Message IDs <br>
    The Java Logging APIs do not provide any direct support for unique message IDs. Those applications or subsystems requiring unique message IDs should define their own conventions and include the unique IDs in the message strings as appropriate. <br>
7) Sample usage <br>
   java.util.logging package. <br>

   package com.wombat; <br>
    import java.util.logging.*; <br>

    public class Nose { <br>
    // Obtain a suitable logger. <br>
    private static Logger logger = Logger.getLogger("com.wombat.nose"); <br>
    public static void main(String argv[]) { <br>
        // Log a FINE tracing message <br>
        logger.fine("doing stuff"); <br>
        try { <br>
            Wombat.sneeze(); <br>
        } catch (Exception ex) { <br>
            // Log the exception <br>
            logger.log(Level.WARNING, "trouble sneezing", ex); <br>
        } <br>
        logger.fine("done"); <br>
    } <br>
    } <br>

    Changing file configuraiton <br>
    public static void main(String[] args) { <br>
    Handler fh = new FileHandler("%t/wombat.log"); <br>
    Logger.getLogger("").addHandler(fh); <br>
    Logger.getLogger("com.wombat").setLevel(Level.FINEST); <br>
    ... <br>
    } <br>
