# Security Enhanced Linux (SELinux)
SELinux, which stands for Security-Enhanced Linux, is a security framework and implementation of mandatory access controls (MAC) in the Linux kernel. It was originally developed by the U.S. National Security Agency (NSA) and later released as open-source software. SELinux provides a highly granular and fine-tuned security model that goes beyond traditional discretionary access controls (DAC) like file permissions and user/group ownership.

## Mandatory Access Controls (MAC)
SELinux enforces mandatory access controls, which means that it enforces security policies set by system administrators or security policies defined by default. This is in contrast to discretionary access controls (DAC), where file owners can define access permissions.
## Security Policies
SELinux uses security policies to define what actions and operations are allowed or denied on a system. These policies are specified in a language called Security Policy Language (SELinux policy language) and are represented as rules.
## Labels
In SELinux, every process, file, and network socket is assigned a label that specifies its security context. Labels include information about the process or object's identity, role, and type. Labels are used to determine what actions are allowed based on security policy rules.
## Roles and Domains
SELinux defines roles (e.g., user, staff, sysadmin) and domains (e.g., httpd_t for Apache web server). Roles and domains are used to specify the security context of processes and objects. Each role and domain has associated permissions.
## Type Enforcement
SELinux uses type enforcement to ensure that only processes with the appropriate security context can access specific files or perform certain operations. This helps prevent unauthorized access and reduces the risk of privilege escalation.

SELinux policies are typically defined in a language called Security Policy Language (SELinux policy language) and are represented as a set of rules and configurations. These policies specify how different processes, users, and objects interact with each other and what actions are allowed or denied. Below is a simplified example of an SELinux policy rule:

```
allow httpd_t var_t:file { read getattr open };
```

- allow: This keyword is used to define an access control rule.
- httpd_t: It represents the source security context, which is typically the context of the process or application seeking access to a resource. In this case, it's the security context for an Apache web server (httpd).
- var_t: This represents the target security context, which is the security context of the resource being accessed. In this case, it's a file labeled with the var_t context.
- file: This specifies the class of the object being accessed. In SELinux, objects are categorized into classes, such as file, directory, socket, etc.
- { read getattr open }: These are the permissions or operations that are allowed. In this example, it allows the httpd process to perform read, getattr (get attributes), and open operations on files labeled with the var_t context.


## Policy Modules
SELinux policies are modular and can be extended or customized using policy modules. This allows system administrators to tailor the security policies to their specific needs.
## Booleans
SELinux policies often include booleans, which are tunable settings that can be used to enable or disable specific security features or behaviors.
