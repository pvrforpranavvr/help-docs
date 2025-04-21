## 🔍 Check for Dependency Conflicts

Dependency conflicts can lead to errors like:

java.lang.NoSuchMethodError

To inspect which version of a dependency is being used:

    mvn dependency:tree -Dincludes=<group-id>:<artifact-id>

Example:

    mvn dependency:tree -Dincludes=org.apache.commons:commons-compress

## 🧯 How to Fix Dependency Conflicts
✅ Option 1: Exclude the conflicting dependency
Exclude the unwanted version from a specific dependency:

    <dependency>
      <groupId>some.group</groupId>
      <artifactId>some-artifact</artifactId>
      <exclusions>
        <exclusion>
          <groupId>org.apache.commons</groupId>
          <artifactId>commons-compress</artifactId>
        </exclusion>
      </exclusions>
    </dependency>

✅ Option 2: Force a specific version using dependencyManagement
Use this when you want to enforce a version globally across all dependencies:

    <dependencyManagement>
      <dependencies>
        <dependency>
          <groupId>org.apache.commons</groupId>
          <artifactId>commons-compress</artifactId>
          <version>1.21</version> <!-- or latest compatible version -->
        </dependency>
      </dependencies>
    </dependencyManagement>

## ℹ️ Useful for avoiding transitive dependency mismatches    

