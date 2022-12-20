# JMeter Robotframework Library

    This is a JMeter Library that allow to integrate JMeter Load Tests with Robotframework.

    Runs JMeter. Returns None.
            Parameters:
                - jmeterPath - path to JMeter executable file
                - testPlanPath - path to jmx file
                - logFilePath - path to a log file
                - otherParams (optional) - other parameters to be called
            Examples:
            | run jmeter | D:/apache-jmeter-2.12/bin/jmeter.bat | D:/Tests/Test1Thread1Loop.jmx | D:/Tests/output1.jtl |
            | run jmeter | D:/apache-jmeter-2.12/bin/jmeter.bat | D:/Tests/Test1Thread1Loop.jmx | D:/Tests/output1.jtl | -H my.proxy.server -P 8000 |


    Runs JMeter and parses log file. Converts results into HTML and SQLite format.
            Returns list of dictionaries containing summary report of parsed output.
            Parameters:
                - jmeterPath - path to JMeter executable file
                - testPlanPath - path to jmx file
                - logFilePath - path to a log file
                - otherParams (optional) - other parameters to be called
                - disableReports - optional paramter for disabling particular parts of html report.
                 It requires integer value which is composed of bits which meaning is
                 as follows (binary numebers in Python notation):
                     0b00000001 -> disable aggregated report and graph;
                     0b00000010 -> disable aggregated samples;
                     0b00000100 -> disable response time graph;
                     0b00001000 -> disable all samples;
                  For example disabling aggr samples and resp time graph needs 0b00000110 which is integer 6.
            Examples:
            | run jmeter analyse jtl convert | D:/apache-jmeter-2.12/bin/jmeter.bat | D:/Tests/Test1Thread1Loop.jmx | D:/Tests/output1.jtl |
            | run jmeter analyse jtl convert | D:/apache-jmeter-2.12/bin/jmeter.bat | D:/Tests/Test1Thread1Loop.jmx | D:/Tests/output1.jtl | -H my.proxy.server -P 8000 |


     Runs JMeter and parses log file. Converts results into SQLite format.
            Returns list of dictionaries containing summary report of parsed output.
            Parameters:
                - jmeterPath - path to JMeter executable file
                - testPlanPath - path to jmx file
                - logFilePath - path to a log file
                - otherParams (optional) - other parameters to be called
            Examples:
            | run jmeter analyse jtl convert to db | D:/apache-jmeter-2.12/bin/jmeter.bat | D:/Tests/Test1Thread1Loop.jmx | D:/Tests/output1.jtl |
            | run jmeter analyse jtl convert to db | D:/apache-jmeter-2.12/bin/jmeter.bat | D:/Tests/Test1Thread1Loop.jmx | D:/Tests/output1.jtl | -H my.proxy.server -P 8000 |


    Runs JMeter and parses log file. Converts results into html format.
            Returns list of dictionaries containing summary report of parsed output.
            Parameters:
                - jmeterPath - path to JMeter executable file
                - testPlanPath - path to jmx file
                - logFilePath - path to a log file
                - otherParams (optional) - other parameters to be called
                - disableReports - optional paramter for disabling particular parts of html report.
                 It requires integer value which is composed of bits which meaning is
                 as follows (binary numebers in Python notation):
                     0b00000001 -> disable aggregated report and graph;
                     0b00000010 -> disable aggregated samples;
                     0b00000100 -> disable response time graph;
                     0b00001000 -> disable all samples;
                  For example disabling aggr samples and resp time graph needs 0b00000110 which is integer 6.
            Examples:
            | run jmeter analyse jtl convert to html | D:/apache-jmeter-2.12/bin/jmeter.bat | D:/Tests/Test1Thread1Loop.jmx | D:/Tests/output1.jtl |
            | run jmeter analyse jtl convert to html | D:/apache-jmeter-2.12/bin/jmeter.bat | D:/Tests/Test1Thread1Loop.jmx | D:/Tests/output1.jtl | -H my.proxy.server -P 8000 |