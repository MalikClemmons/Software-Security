# CS 305 – Software Security Portfolio

Malik Clemmons

This portfolio includes my Artemis Financial Practices for Secure Software Report from Project Two. The report explains the security changes I made to a Java Spring Boot application and includes screenshots and testing results.

## Portfolio Artifact

[Artemis Financial Practices for Secure Software Report](CS_305_Project_Two_Report.docx)

## Client and Software Requirements

Artemis Financial is a financial consulting company that creates individualized plans for customers, including savings, retirement, investments, and insurance. The company needed to improve the security of its web application and protect information being transferred. My work focused on adding HTTPS for secure communication and SHA-256 checksum verification to check whether data had changed.

## Finding Vulnerabilities and Coding Securely

I did well at following up on the scanner results instead of stopping after the application worked. The initial completed dependency scan identified vulnerabilities in the embedded Tomcat dependency. I updated the dependency and ran the scan again to check the results. Secure coding matters because an application can work correctly while still exposing customer information. For a company like Artemis Financial, software security helps protect customer trust, reduce the chance of data breaches, and avoid interruptions and recovery costs.

## Challenges and Helpful Parts of the Assessment

One challenging part was getting the dependency scan to run correctly and understanding the difference between a scanner configuration issue and a vulnerability in the application. Working through the Maven settings and reviewing the generated report helped me understand what the scan actually checked. It also showed me why BUILD SUCCESS alone does not tell the whole story. I still needed to review the findings and any warnings about scan coverage.

## Adding Layers of Security

I added several layers that addressed different risks. HTTPS and TLS protected information in transit, while the locally trusted certificate supported server identity verification during testing. SHA-256 checked the demonstration data against an expected checksum. I also validated the expected digest, kept the keystore password in the run environment, limited detailed error responses, and updated vulnerable dependencies. In future projects, I would combine dependency scanning, manual code review, automated security checks, and current vendor advisories. I would choose mitigations based on the severity of a finding, how the affected component is used, and the potential impact on the application.

## Checking Functionality and Security

I reviewed the Java code, Maven configuration, and HTTPS settings, then ran automated tests and checked the application in the browser. The tests covered the checksum output, rejection of changed data, invalid expected digests, and the controller response. All four automated tests passed, and the application returned a verified checksum over HTTPS. After updating Tomcat, I rebuilt the project, repeated the live HTTPS check, and reran Dependency-Check. The final scan reported zero known vulnerabilities with no suppressions. However, the OSS Index analyzer was unavailable, so I would not treat that result as proof that every possible weakness had been eliminated.

## Useful Tools and Practices

Eclipse, Maven, OWASP Dependency-Check, Java Keytool, and Java's MessageDigest API were useful throughout this project. I also used an independently calculated checksum to verify the application's result. Practices I would carry forward include using established cryptographic APIs, keeping credentials out of source code, checking dependencies regularly, and testing again after making security changes. Keeping screenshots and clear notes also made it easier to explain and reproduce my work.

## Work to Show Future Employers

I would show employers the completed report because it connects the client's requirements to the changes I made and the evidence used to check them. The before-and-after dependency scan results, checksum verification, HTTPS screenshots, and automated test results demonstrate my ability to identify a security issue, apply a fix, and verify that the application still works. This project also shows that I can explain both the benefits and the limits of the security controls I implement.
