1) The Preferences API enables applications to manage preference and configuration data. <br>
2) The java.util.prefs package provides a way for applications to store and retrieve user and system preference and configuration data. The data is stored persistently in an implementation-dependent backing store. There are two separate trees of preference nodes: one for user preferences and one for system preferences. <br>
3) All of the methods that modify preference data are permitted to operate asynchronously. They may return immediately, and changes will eventually propagate to the persistent backing store. The flush method can be used to force changes to the backing store. <br>
4) Example1 <br>
    Preferences prefs = Preferences.userNodeForPackage(Gadget.class); <br>
        int numRows = prefs.getInt(NUM_ROWS, 40); <br>
        int numCols = prefs.getInt(NUM_COLS, 80); <br>
    Example2:  <br>
    Preferences prefs = Preferences.systemNodeForPackage(Gadget.class); <br>
    Example3: <br>
    static String ourNodeName = "/com/greencorp/widget"; <br>
    static void getPrefs() { <br>
    Preferences prefs = Preferences.userRoot().node(ourNodeName); <br>
    ... <br>
    } <br>
    Example4: <br>
    static Preferences prefs =  Preferences.systemRoot().node(ourNodeName); <br>

5) Where is the default backing store? <br>

    System and user preference data is stored persistently in an implementation-dependent backing store. Typical implementations include flat files, OS-specific registries, directory servers and SQL databases. For example, on Windows systems the data is stored in the Windows registry. <br>

    On Linux systems, the system preferences are typically stored at java-home/.systemPrefs in a network installation, or /etc/.java/.systemPrefs in a local installation. If both are present, /etc/.java/.systemPrefs takes precedence. The system preferences location can be overridden by setting the system property java.util.prefs.systemRoot. The user preferences are typically stored at user-home/.java/.userPrefs. The user preferences location can be overridden by setting the system property java.util.prefs.userRoot. <br>