# grails-dc
It is an example use of dependency check gradle plugin for grails 3.2.7 project

I have introduced the dependency check call as dependent on the war phase. So typically a
```bash
./gradlew dependencyCheckAnalyze -Ddownloader.quick.query.timestamp=false -Pformat=ALL --refresh-dependencies
```
should generate a report in
```bash
build/reports/dependency-check-report.html
```
In the folder 
```bash
build/libs
```
, there is a war (helloworld-0.1.war) which I unzip through MacOS. Then, I navigate to the folder
```bash
helloworld-0.1/WEB-INF/lib
```
where I run (CLI is installed through brew)
```bash
dependency-check   --project "My App Name" --suppression ../../../../../owasp-suppressions.xml  --scan "."
```

and a new  report is generated (dependency-check-report.html).
