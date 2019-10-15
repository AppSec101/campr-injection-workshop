# **Campr Injection Workshop**

This is a deliberately vulnerable application to test a simple SQL Injection.

## **Running in Docker**

---

## Requirements

- Docker desktop > 2.1
  ```bash
  brew cask install docker
  ```
- A Java IDE _e.g, IntelliJ IDEA_ (an IDE is recommended, not mandatory. An editor will do just fine, if you are comfortable with it)

## Steps to complete the workshop

1. Run the application

  ```
    git clone git@github.com:AppSec101/campr-injection-workshop.git
  ```
  (ignore the above step if already cloned)

  ```
    cd campr-injection-workshop
  ```

   ```bash
   docker-compose rm -f && docker-compose up
   ```

2. Open the application at http://localhost:8080/

3. Run tests. `login_should_not_be_vulnerable_to_obvious_sql_injection` test should fail

   ```bash
   docker exec -it campr-injection-workshop /bin/sh -c 'cd app && ./gradlew -g /app/.gradle test'
   ```

4. You can test further or fix the bug in the code to fix the injection flaw. Run tests again to see them passing. Do you have to write more tests to cover more scenarios?

5. Once the test passes, Restart the application
   ```bash
   docker-compose rm -f && docker-compose up
   ```
6. Open the application & verify the bug is fixed http://localhost:8080/

7. That's it. Stop the services and do clean up.
REMEMBER TO DO THIS STEP. LEAVING THE SERVER RUNNING COULD PUT YOUR COMPUTER AT RISK DUE TO THE VULNERABLE APPLICATION

   ```bash
   docker-compose rm -f
   ```
