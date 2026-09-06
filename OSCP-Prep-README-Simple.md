# OSCP+ Preparation Repository

A comprehensive, lab-first preparation roadmap for OSCP+ and PEN-200 style penetration testing.

Use this README as the master syllabus. Work through each topic, build a lab, practice the technique, document what you learned, and repeat the workflow until you can perform it without a walkthrough.

A deep, lab-first study roadmap for preparing for the **OffSec OSCP+ / PEN-200** style of practical penetration testing.

**Important:** This repository is an educational framework. Use exploitation, credential attacks, tunneling, and post-exploitation techniques only in systems and environments you own or are explicitly authorized to assess. Always verify the current OffSec exam guide, rules, syllabus, and permitted tooling before your exam.

## Table of Contents

1. [How to Use This Repository](#how-to-use-this-repository)
2. [OSCP+ Skill Model](#oscp-skill-model)
3. [01 — Foundations](#01--foundations)
4. [02 — Information Gathering and Enumeration](#02--information-gathering-and-enumeration)
5. [03 — Vulnerability Identification](#03--vulnerability-identification)
6. [04 — Web Application Security](#04--web-application-security)
7. [05 — Exploitation](#05--exploitation)
8. [06 — Password Attacks](#06--password-attacks)
9. [07 — Windows Privilege Escalation](#07--windows-privilege-escalation)
10. [08 — Linux Privilege Escalation](#08--linux-privilege-escalation)
11. [09 — Tunneling, Pivoting, and Port Forwarding](#09--tunneling-pivoting-and-port-forwarding)
12. [10 — Metasploit](#10--metasploit)
13. [11 — Active Directory](#11--active-directory)
14. [12 — Post-Exploitation and Lateral Movement](#12--post-exploitation-and-lateral-movement)
15. [13 — AWS / Cloud Fundamentals](#13--aws--cloud-fundamentals)
16. [14 — Evidence Collection](#14--evidence-collection)
17. [15 — Reporting](#15--reporting)
18. [16 — Exam Methodology](#16--exam-methodology)
19. [17 — Practice Methodology](#17--practice-methodology)
20. [18 — Checklists](#18--checklists)
21. [19 — Note-Taking System](#19--note-taking-system)
22. [20 — Lab Architecture](#20--lab-architecture)
23. [21 — Study Plan](#21--study-plan)
24. [22 — Completion Criteria](#22--completion-criteria)
25. [23 — References](#23--references)

# How to Use This Repository

This repository is organized around a repeatable penetration-testing workflow rather than a collection of commands to memorize.

For every target:

```text
Observe
  ↓
Enumerate
  ↓
Identify attack surface
  ↓
Form hypotheses
  ↓
Validate hypotheses
  ↓
Exploit
  ↓
Stabilize access
  ↓
Enumerate locally
  ↓
Privilege escalation
  ↓
Pivot / lateral movement
  ↓
Collect evidence
  ↓
Document
  ↓
Remediate
```

### The five questions to ask continuously

1. **What do I know?**
2. **What don't I know?**
3. **What evidence supports my current hypothesis?**
4. **What is the next highest-value test?**
5. **If this path fails, what alternative path remains?**

### Do not rely on blind tool output

A scanner finding is a lead, not automatically a vulnerability.

For each finding, determine:

- What is actually exposed?
- What version/configuration is running?
- Is the finding applicable?
- Can it be safely validated?
- What is the security impact?
- What evidence proves the issue?
- What remediation would eliminate it?

# OSCP+ Skill Model

The preparation program should build competency in the following areas:

Skill domains:
1. Foundations: Understand networking, operating systems, authentication, scripting, and security concepts
1. Enumeration: Build a complete attack-surface map from limited information
1. Vulnerability identification: Convert service/application observations into validated attack hypotheses
1. Exploitation: Obtain controlled access through appropriate attack paths
1. Privilege escalation: Turn low-privilege access into higher-privilege access
1. Web security: Analyze and exploit common web application weaknesses in a lab
1. Active Directory: Enumerate domains, authentication, trust, permissions, and attack paths
1. Pivoting: Reach otherwise inaccessible network segments
1. Post-exploitation: Enumerate, authenticate, move laterally, and collect proof
1. Documentation: Produce reproducible technical evidence and professional findings
1. Time management: Make rational decisions under exam-style time constraints

# 01 — Foundations

## 1.1 Networking Fundamentals

### OSI and TCP/IP

- OSI model
- TCP/IP model
- Layer responsibilities
- Encapsulation
- Frames, packets, segments, datagrams
- MTU and fragmentation

### Addressing

- IPv4
- IPv6 fundamentals
- CIDR
- Subnet masks
- Network/broadcast/host addresses
- Private address ranges
- Loopback
- Link-local addressing
- NAT
- PAT

### Core protocols

- Ethernet
- ARP
- ICMP
- TCP
- UDP
- DNS
- DHCP
- HTTP/HTTPS
- SSH
- FTP
- SMTP
- SMB
- LDAP
- Kerberos
- RDP
- SNMP

### TCP concepts

- Three-way handshake
- Flags
- Ports
- Connection states
- Retransmission
- Windowing
- Service identification

### Routing

- Default gateway
- Routing tables
- Static routes
- Network segmentation
- VLAN concepts
- Firewalls
- ACLs

## 1.2 Linux Fundamentals

### Filesystem

- `/etc`
- `/var`
- `/tmp`
- `/home`
- `/opt`
- `/usr`
- `/proc`
- `/sys`
- `/dev`

### Permissions

- Owner/group/other
- Read/write/execute
- Numeric permissions
- Special permissions
- SUID
- SGID
- Sticky bit
- ACLs

### Processes

- PID
- PPID
- Process ownership
- Signals
- Foreground/background jobs
- Process trees
- Services/daemons

### Shell

- Bash fundamentals
- Variables
- Environment variables
- Pipes
- Redirection
- Command substitution
- Globbing
- Quoting
- Exit codes
- Loops
- Conditionals

### Administration

- Users
- Groups
- sudo
- cron
- systemd
- logs
- mounted filesystems
- networking
- package management

## 1.3 Windows Fundamentals

### Architecture

- Windows kernel/user mode
- Processes
- Services
- DLLs
- Registry
- Security principals

### Accounts and groups

- Local users
- Local groups
- Administrators
- Service accounts
- Security identifiers
- Access tokens

### Filesystem

- NTFS
- ACLs
- Alternate data streams
- Shares
- Windows directories

### Services and tasks

- Windows services
- Scheduled tasks
- Startup mechanisms
- Service accounts
- Service permissions

### Windows administration

- PowerShell
- CMD
- Event logs
- Registry
- WMI
- WinRM
- RDP

## 1.4 Programming and Scripting

### Bash

- Variables
- Functions
- Loops
- Conditions
- Text processing
- Command pipelines

### Python

- Data types
- Functions
- File I/O
- Sockets
- HTTP requests
- Argument parsing
- Exception handling
- Encoding/decoding

### PowerShell

- Objects
- Cmdlets
- Pipelines
- Variables
- Functions
- Remote execution
- Windows enumeration

### General exploit-development literacy

- Source-code reading
- Debugging
- Input/output handling
- Compilers/interpreters
- Dependency management
- Translating PoCs
- Adapting exploit parameters

## 1.5 Cryptography Fundamentals

- Encoding vs encryption vs hashing
- Base64
- Hex
- URL encoding
- Hashes
- Salts
- Password hashing
- Symmetric encryption
- Asymmetric encryption
- Digital signatures
- Certificates
- TLS basics
- Public/private keys
- Common cryptographic mistakes

# 02 — Information Gathering and Enumeration

# 2.1 Passive Information Gathering

- Domain information
- DNS records
- WHOIS/RDAP concepts
- Certificate transparency
- Search-engine reconnaissance
- Public code repositories
- Public documentation
- Metadata
- Technology identification
- Username discovery
- Organization mapping
- Publicly exposed credentials/secrets awareness

## 2.2 Active Information Gathering

- Host discovery
- Port scanning
- Service discovery
- Version detection
- OS fingerprinting
- Script-assisted enumeration
- UDP discovery
- TCP discovery
- Full-port enumeration
- Target prioritization

## 2.3 Nmap

Understand:

- Host discovery
- TCP SYN scanning
- TCP connect scanning
- UDP scanning
- Port ranges
- Service/version detection
- OS detection
- NSE concepts
- Timing
- Output formats
- IPv6 considerations
- Scan interpretation
- Avoiding incomplete scans

## 2.4 DNS Enumeration

- A/AAAA
- CNAME
- MX
- NS
- TXT
- SOA
- PTR
- SRV
- DNS zone concepts
- Reverse lookups
- Subdomain discovery
- Zone transfer concepts
- Internal DNS enumeration

## 2.5 SMB Enumeration

- SMB versions
- Shares
- Anonymous access
- Null sessions
- Users
- Groups
- Domain information
- Share permissions
- File discovery
- Authentication
- SMB signing concepts

## 2.6 FTP Enumeration

- Anonymous access
- Banner/version
- Directory listing
- File retrieval
- Upload permissions
- Encryption considerations

## 2.7 SSH Enumeration

- Version
- Authentication methods
- Usernames
- Key-based authentication
- Configuration weaknesses
- Tunneling capabilities

## 2.8 SMTP Enumeration

- SMTP commands
- Banner
- User enumeration concepts
- Relay concepts
- Mail infrastructure mapping

## 2.9 SNMP Enumeration

- SNMP versions
- Community strings
- MIB concepts
- System information
- Network information
- User/process/configuration disclosure

## 2.10 LDAP Enumeration

- LDAP directory concepts
- Naming contexts
- Base DN
- Anonymous bind
- Users
- Groups
- Computers
- Organizational units
- Attributes

## 2.11 HTTP Enumeration

- Web server identification
- Technologies
- Headers
- Methods
- Status codes
- Virtual hosts
- Directories
- Files
- Parameters
- Authentication
- Cookies
- Sessions
- TLS configuration

## 2.12 RDP / WinRM Enumeration

- RDP exposure
- Authentication
- NLA concepts
- WinRM
- PowerShell remoting
- Management interfaces

# 03 — Vulnerability Identification

## 3.1 Vulnerability Research

- CVE
- CWE
- CVSS
- Vendor advisories
- Security advisories
- Exploit databases
- Public PoCs
- Git repositories
- Version matching
- Configuration-dependent vulnerabilities

## 3.2 Vulnerability Validation

For every candidate:

1. Identify affected component.
2. Confirm exact version/configuration.
3. Understand prerequisites.
4. Reproduce in a lab where possible.
5. Determine expected behavior.
6. Validate impact.
7. Record evidence.

## 3.3 Common Vulnerability Classes

- Authentication weaknesses
- Authorization weaknesses
- Injection
- Memory corruption concepts
- Path traversal
- File inclusion
- Command injection
- Unsafe file upload
- Information disclosure
- Misconfiguration
- Default credentials
- Weak permissions
- Exposed secrets
- Insecure services

## 3.4 Automated Scanning

Understand the role and limitations of:

- Port scanners
- Web scanners
- Vulnerability scanners
- Enumeration scripts

Learn:

- False positives
- False negatives
- Scanner validation
- Manual confirmation
- Prioritization

# 04 — Web Application Security

## 4.1 HTTP Fundamentals

- Request/response structure
- Methods
- Headers
- Cookies
- Sessions
- Status codes
- Content types
- URL structure
- Query parameters
- POST bodies
- Authentication headers
- Redirects
- Caching
- TLS

## 4.2 Web Enumeration

- Technology fingerprinting
- Directory discovery
- File discovery
- Virtual host discovery
- Parameter discovery
- API discovery
- Backup files
- Source-code review
- JavaScript analysis
- Robots.txt
- Sitemap
- Error messages
- Debug interfaces

## 4.3 Authentication

- Username/password authentication
- Session management
- Password reset
- Account enumeration
- Weak credentials
- Authentication bypass concepts
- MFA concepts
- Token handling

## 4.4 Authorization

- Horizontal privilege escalation
- Vertical privilege escalation
- IDOR/BOLA
- Access-control failures
- Missing authorization checks

## 4.5 Injection

- SQL injection
- Command injection
- LDAP injection
- Template injection concepts
- Header injection
- Expression-language injection concepts

## 4.6 SQL Injection

### Understand

- SQL syntax
- SELECT
- WHERE
- UNION
- INSERT/UPDATE/DELETE concepts
- Comments
- Operators
- String handling

### Attack concepts

- Error-based
- Union-based
- Boolean-based
- Time-based
- Authentication bypass
- Data extraction
- Database fingerprinting

### Databases

- MySQL/MariaDB
- PostgreSQL
- Microsoft SQL Server
- SQLite
- Basic database privilege concepts

## 4.7 Cross-Site Scripting

- Reflected XSS
- Stored XSS
- DOM XSS
- Contexts
- Output encoding
- Input filtering
- Session/security impact

## 4.8 File Inclusion

- Local file inclusion
- Remote file inclusion concepts
- Path normalization
- Traversal
- Wrapper concepts
- Log/file inclusion concepts

## 4.9 Path Traversal

- Relative paths
- Absolute paths
- Encoding
- Normalization
- Filtering bypass concepts
- Windows vs Linux paths

## 4.10 File Upload

- Extension validation
- MIME validation
- Content validation
- Filename handling
- Storage location
- Web-accessible uploads
- Server-side processing
- Safe validation in a lab

## 4.11 Command Injection

- Shell metacharacters
- Command separators
- Output handling
- Blind command execution
- Context differences
- Input validation failures

## 4.12 SSRF

- Server-side request concepts
- Internal services
- URL parsing
- Allowlist/denylist failures
- Cloud metadata concepts

## 4.13 APIs

- REST
- JSON
- Authentication
- Authorization
- Object identifiers
- HTTP methods
- API documentation
- Parameter tampering
- Rate limiting
- Error handling

## 4.14 Client-Side Attacks

- Browser trust boundaries
- JavaScript
- DOM
- Client-side validation
- Dangerous browser APIs
- Social-engineering awareness
- File/protocol handling concepts

# 05 — Exploitation

## 5.1 Exploitation Methodology

- Initial access
- Preconditions
- Payload selection
- Reliability
- Stability
- Shell quality
- Architecture
- Privilege level
- Post-exploitation enumeration

## 5.2 Public Exploits

- Search by product/version
- Read source code
- Identify prerequisites
- Build dependencies
- Test in a lab
- Modify parameters
- Troubleshoot failures
- Validate success

## 5.3 Exploit Modification

Learn to modify:

- IP addresses
- Ports
- URLs
- File paths
- Usernames
- Payloads
- Encodings
- Headers
- Architecture-specific values
- Compiler/build settings

## 5.4 Payload Concepts

- Reverse shells
- Bind shells
- Web shells
- Staged vs non-staged concepts
- Shell stabilization
- PTY concepts
- Windows shell environments
- PowerShell sessions

## 5.5 Exploit Troubleshooting

When an exploit fails:

- Verify target version
- Verify architecture
- Verify connectivity
- Verify listener
- Verify payload
- Check required files/dependencies
- Read the PoC
- Reproduce manually
- Reduce complexity
- Test one assumption at a time

## 5.6 Exploit Development Literacy

- Memory layout concepts
- Stack/heap concepts
- Registers
- Instruction pointers
- Calling conventions
- Buffer-overflow terminology
- Bad characters
- Crash analysis
- Offset concepts
- Shellcode concepts
- Mitigation concepts

# 06 — Password Attacks

## 6.1 Credential Discovery

- Configuration files
- Environment variables
- Application secrets
- Source code
- Backup files
- Command history
- Credential stores
- Password reuse
- Documentation

## 6.2 Password Attacks

- Online authentication testing
- Offline hash analysis
- Wordlists
- Rules
- Masks
- Credential spraying concepts
- Password reuse
- Default credentials
- Weak credentials

## 6.3 Hashes

- Identify hash formats
- Understand salts
- Understand work factors
- Offline cracking workflow
- Credential validation

## 6.4 Windows Credential Material

- NTLM concepts
- NTLM hashes
- Credential Manager concepts
- SAM concepts
- LSA secrets concepts
- Kerberos tickets

## 6.5 Password Attack Safety

- Rate limiting
- Lockout awareness
- Scope restrictions
- Evidence preservation
- Avoiding unnecessary account disruption

# 07 — Windows Privilege Escalation

## 7.1 Local Enumeration

Collect:

- Current user
- Groups
- Privileges
- OS version
- Architecture
- Hostname
- Network configuration
- Routes
- Processes
- Services
- Scheduled tasks
- Installed software
- Environment variables
- Interesting files
- Credentials/secrets
- Security products

## 7.2 Windows Services

- Service enumeration
- Service permissions
- Binary paths
- Writable binaries
- Writable directories
- Unquoted service paths
- Service configuration weaknesses

## 7.3 Scheduled Tasks

- Enumeration
- Task ownership
- Executable permissions
- Script permissions
- Writable task paths
- Credentials/configuration exposure

## 7.4 File and Directory Permissions

- Writable system locations
- Writable executables
- DLL search-order concepts
- Configuration files
- Backup files
- Sensitive directories

## 7.5 Registry

- Registry structure
- Run keys
- Service configuration
- Application configuration
- Stored credentials
- Registry permissions

## 7.6 Tokens and Privileges

Understand:

- Access tokens
- Integrity levels
- User rights
- Dangerous privileges
- Service accounts
- Impersonation concepts

## 7.7 UAC and Windows Security Controls

- UAC concepts
- Integrity levels
- Defender concepts
- Application control concepts
- Security boundaries

## 7.8 Credential Hunting

- Configuration files
- Scripts
- PowerShell history
- Application data
- Shares
- Registry
- Credential stores

# 08 — Linux Privilege Escalation

## 8.1 Local Enumeration

Collect:

- Current user
- UID/GID
- Groups
- Kernel
- OS
- Architecture
- Hostname
- Interfaces
- Routes
- Processes
- Services
- Cron
- Mounted filesystems
- Installed packages
- Environment
- Interesting files

## 8.2 sudo

Understand:

- sudo permissions
- Command restrictions
- Environment behavior
- NOPASSWD
- Sudoers configuration
- Dangerous delegated commands

## 8.3 SUID/SGID

- Finding SUID binaries
- Finding SGID binaries
- Understanding expected system binaries
- Identifying unusual binaries
- Permission analysis

## 8.4 Capabilities

- Linux capabilities
- File capabilities
- Process capabilities
- Dangerous capability configurations

## 8.5 Cron

- System cron
- User cron
- Writable scripts
- Writable directories
- PATH issues
- Environment issues

## 8.6 Services

- systemd
- Init scripts
- Service configuration
- Writable service files
- Service execution context

## 8.7 Filesystem Weaknesses

- Writable directories
- Writable executables
- Misowned files
- Configuration files
- Backups
- Temporary files
- SSH keys

## 8.8 Kernel Exploitation

Understand:

- Kernel versions
- Local kernel vulnerabilities
- Preconditions
- Reliability
- Why kernel exploits should generally be considered after simpler paths

## 8.9 Credential Hunting

Search conceptually for:

- Passwords
- API keys
- SSH keys
- Tokens
- Configuration secrets
- Database credentials
- Shell history
- Application files

# 09 — Tunneling, Pivoting, and Port Forwarding

## 9.1 Networking Through a Compromised Host

Understand:

- Reachability
- Routing
- Listening sockets
- Bind addresses
- NAT
- Firewalls
- Network segmentation

## 9.2 Port Forwarding

- Local port forwarding
- Remote port forwarding
- Dynamic forwarding
- SOCKS concepts

## 9.3 SOCKS Proxies

- Proxy-based access
- Tool proxy configuration
- DNS considerations
- TCP limitations
- Operational troubleshooting

## 9.4 Pivoting

- Identify interfaces
- Identify routes
- Identify internal subnets
- Enumerate reachable services
- Establish tunnel
- Scan through tunnel
- Access internal services
- Document the route

## 9.5 Multi-Hop Concepts

- Pivot A → Pivot B
- Nested tunnels
- Route management
- Operational complexity
- Failure isolation

# 10 — Metasploit

## 10.1 Framework Structure

- Modules
- Exploits
- Payloads
- Auxiliary modules
- Post modules
- Encoders
- Sessions

## 10.2 Core Workflow

- Search
- Info
- Options
- Set parameters
- Run
- Background
- Session management

## 10.3 Payload Concepts

- Staged
- Non-staged
- Architecture
- Platform
- Transport

## 10.4 Sessions

- Shell sessions
- Meterpreter concepts
- Backgrounding
- Session enumeration
- File operations
- Process enumeration
- Post-exploitation modules

## 10.5 Exploit Validation

- Read module documentation
- Verify target
- Understand reliability
- Understand payload behavior
- Collect evidence

## 10.6 Manual vs Framework Exploitation

Know when to:

- Use a framework
- Use a public PoC
- Modify a PoC
- Reproduce manually
- Fall back to another technique

# 11 — Active Directory

# 11.1 AD Architecture

Understand:

- Domain
- Forest
- Tree
- Domain Controller
- Organizational Unit
- Users
- Groups
- Computers
- Group Policy
- Sites
- Trusts
- DNS integration

## 11.2 Identity and Authentication

### Kerberos

- KDC
- AS-REQ
- AS-REP
- TGT
- TGS
- Service principals
- SPNs
- Ticket lifetime
- Delegation concepts

### NTLM

- Challenge-response
- NTLM hashes
- Pass-the-Hash concepts
- Authentication flow

### LDAP

- Directory queries
- Attributes
- Distinguished names
- Search bases
- Authentication/bind concepts

## 11.3 AD Enumeration

Enumerate:

- Domain
- Domain controllers
- Users
- Groups
- Computers
- Shares
- SPNs
- GPOs
- Trusts
- ACLs
- Delegation
- Password policy
- Logged-on users
- Sessions
- Local administrators

## 11.4 SMB in AD

- Domain shares
- Administrative shares
- Share permissions
- NTFS permissions
- Authentication
- Signing
- Remote management

## 11.5 LDAP in AD

- Domain naming context
- User objects
- Group objects
- Computer objects
- Service accounts
- SPNs
- Group membership
- Delegated permissions

## 11.6 Kerberos Attack Concepts

Understand and recognize:

- AS-REP roasting
- Kerberoasting
- Ticket-based authentication
- Service account exposure
- Password strength implications
- Ticket extraction concepts
- Pass-the-Ticket concepts

## 11.7 NTLM Attack Concepts

- NTLM hash exposure
- Pass-the-Hash concepts
- Relay concepts
- SMB/HTTP authentication
- Signing protections

## 11.8 Password and Account Attacks in AD

- Password spraying
- Weak passwords
- Reused passwords
- Default credentials
- Account lockout policy
- Service account credentials

## 11.9 Group and Permission Abuse

Understand:

- Nested groups
- Local administrator membership
- Domain group membership
- ACLs
- ACEs
- Generic permissions
- Object ownership
- Write permissions
- DACL concepts

## 11.10 AD ACL Attack Paths

Study the security implications of permissions such as:

- GenericAll
- GenericWrite
- WriteDACL
- WriteOwner
- AddMember
- ForceChangePassword
- WriteProperty
- Extended rights

Focus on:

- Who controls the object?
- What object is controlled?
- What permission exists?
- What security boundary does that permission cross?
- What is the shortest path to the objective?

## 11.11 Delegation

- Unconstrained delegation
- Constrained delegation
- Resource-based constrained delegation
- Service accounts
- Trust boundaries

## 11.12 Group Policy

- GPO structure
- GPO links
- Security filtering
- Scripts
- Preferences
- Policy inheritance
- Misconfiguration risks

## 11.13 Domain Trusts

- Trust direction
- Transitivity
- Parent/child relationships
- Forest trusts
- Cross-domain authentication concepts

## 11.14 AD Attack Graph Thinking

Represent paths as:

```text
Principal
   ↓
Permission / Credential / Authentication Material
   ↓
Object
   ↓
New Privilege
   ↓
New Principal
   ↓
Objective
```

# 12 — Post-Exploitation and Lateral Movement

## 12.1 Post-Exploitation Enumeration

- User context
- Groups
- Privileges
- Processes
- Services
- Network connections
- Routes
- Credentials
- Applications
- Shares
- Security controls

## 12.2 Situational Awareness

Determine:

- What host am I on?
- What accounts exist?
- What networks can I reach?
- What machines can this host reach?
- What credentials/material can I access?
- What services are locally exposed?
- What new attack surface has appeared?

## 12.3 Lateral Movement Concepts

- SMB
- WinRM
- RDP
- SSH
- Remote service execution
- Scheduled-task-based movement concepts
- Credential reuse
- Ticket-based authentication

## 12.4 Credential Material

Understand:

- Passwords
- Hashes
- Tokens
- Tickets
- Keys
- Application credentials
- Service credentials

## 12.5 Data Collection

- Proof files
- Screenshots
- Command output
- Target identity
- Privilege evidence
- Network path evidence

# 13 — AWS / Cloud Fundamentals

Cloud material should be treated according to the current official course/exam scope. Do not assume that every cloud module is exam-tested.

## 13.1 AWS Architecture

- Regions
- Availability Zones
- VPC
- Subnets
- Security groups
- IAM
- EC2
- S3
- Lambda concepts

## 13.2 IAM

- Users
- Groups
- Roles
- Policies
- Permissions
- Trust policies
- Least privilege

## 13.3 Cloud Security Concepts

- Metadata services
- Temporary credentials
- Instance roles
- Storage exposure
- Security groups
- Identity boundaries
- Secret management

## 13.4 Cloud Enumeration

- Public resources
- IAM configuration
- Storage permissions
- Network exposure
- Instance metadata concepts

# 14 — Evidence Collection

## 14.1 Evidence Requirements

For each successful path, capture:

- Target IP/hostname
- Date/time if relevant
- Initial access method
- Account/context
- Commands
- Output
- Vulnerability evidence
- Privilege evidence
- Proof/flag evidence
- Pivot route if applicable

## 14.2 Evidence Quality

Good evidence is:

- Reproducible
- Specific
- Minimal
- Legible
- Contextual
- Sufficient to prove impact

## 14.3 Screenshot Discipline

Capture screenshots that show:

- Target identity
- Command
- Result
- Privilege level
- Relevant file/object
- Context

Avoid screenshots that contain:

- Unnecessary unrelated output
- Sensitive data outside scope
- Ambiguous results

# 15 — Reporting

## 15.1 Executive Summary

Include:

- Assessment objective
- Scope
- Overall security posture
- Major findings
- Business/security impact
- High-level remediation themes

## 15.2 Finding Structure

Every technical finding should contain:

1. Title
2. Severity
3. Affected host/application
4. Description
5. Technical details
6. Reproduction steps
7. Evidence
8. Impact
9. Remediation
10. References where appropriate

## 15.3 Reproduction Steps

A third party should be able to understand:

```text
Initial condition
→ Enumeration
→ Vulnerability
→ Exploitation
→ Result
→ Evidence
```

## 15.4 Remediation

Recommendations should address the root cause:

- Patch
- Remove exposure
- Fix permissions
- Rotate credentials
- Enforce least privilege
- Harden authentication
- Segment networks
- Fix application validation
- Improve monitoring

## 15.5 Attack Narrative

Write the complete chain:

```text
External exposure
→ Enumeration
→ Initial access
→ Credential discovery
→ Privilege escalation
→ Pivot
→ AD compromise / objective
```

# 16 — Exam Methodology

## 16.1 Before Starting

Prepare:

- Notes
- Checklists
- Reporting template
- Terminal layout
- Evidence directory
- Time budget
- Known-good lab procedures

## 16.2 Per-Target Workflow

### Phase 1 — Enumeration

- Identify all ports
- Identify services
- Identify versions
- Enumerate each service
- Record findings

### Phase 2 — Hypothesis Generation

For every service:

- What information did I obtain?
- What authentication exists?
- What files/resources exist?
- What vulnerabilities apply?
- Are credentials available?
- Is there a configuration weakness?

### Phase 3 — Exploitation

- Select highest-probability path
- Validate prerequisites
- Exploit
- Stabilize shell
- Record evidence

### Phase 4 — Privilege Escalation

- Enumerate locally
- Check credentials
- Check permissions
- Check services/tasks
- Check SUID/sudo/capabilities
- Check Windows privileges/services/tasks
- Validate candidates

### Phase 5 — Pivoting

- Enumerate routes/interfaces
- Identify new subnet
- Identify reachable hosts/services
- Establish tunnel
- Enumerate internal target

### Phase 6 — Evidence

Immediately record:

- What worked
- Exact path
- Commands
- Credentials/material
- Proof

## 16.3 Time Management

Use explicit timeboxes.

If a technique produces no new information:

1. Re-check assumptions.
2. Try one controlled variation.
3. Return to enumeration.
4. Move to another attack surface.

Avoid spending an uncontrolled amount of time repeatedly modifying the same exploit.

# 17 — Practice Methodology

## 17.1 Machine Practice

For every practice machine record:

- Initial information
- Open ports
- Services
- Versions
- Web findings
- Credentials
- Exploit path
- Initial shell
- Privilege escalation path
- Pivot path
- Final objective
- Failed approaches
- Lessons learned

## 17.2 Repetition

Repeat each technique at least three ways:

1. With notes.
2. With a checklist only.
3. From a blank terminal.

## 17.3 Blind Enumeration Drills

Practice starting with only:

- IP address
- Hostname
- URL
- Credential pair
- Compromised host

Then build the attack surface yourself.

## 17.4 Failure Analysis

For every failed attempt classify the failure:

- Wrong target
- Wrong version
- Missing prerequisite
- Wrong architecture
- Network issue
- Authentication issue
- Payload issue
- Permission issue
- Tool misuse
- Incorrect hypothesis

# 18 — Checklists

## 18.1 Initial Enumeration Checklist

- [ ] Host discovery
- [ ] Full TCP scan
- [ ] Relevant UDP scan
- [ ] Service/version detection
- [ ] OS identification
- [ ] DNS enumeration
- [ ] SMB enumeration
- [ ] FTP enumeration
- [ ] SSH enumeration
- [ ] SMTP enumeration
- [ ] SNMP enumeration
- [ ] LDAP enumeration
- [ ] HTTP/HTTPS enumeration
- [ ] RDP enumeration
- [ ] WinRM enumeration
- [ ] Virtual host discovery
- [ ] Directory/file discovery
- [ ] Credential discovery
- [ ] Vulnerability research

## 18.2 Linux PrivEsc Checklist

- [ ] `id`
- [ ] `sudo` permissions
- [ ] Groups
- [ ] SUID
- [ ] SGID
- [ ] Capabilities
- [ ] Cron
- [ ] Services
- [ ] Writable paths
- [ ] Writable executables
- [ ] PATH issues
- [ ] Environment variables
- [ ] SSH keys
- [ ] Configuration files
- [ ] Shell history
- [ ] Credentials
- [ ] Processes
- [ ] Network connections
- [ ] Kernel/version review

## 18.3 Windows PrivEsc Checklist

- [ ] Current user
- [ ] Groups
- [ ] Privileges
- [ ] OS/version
- [ ] Architecture
- [ ] Processes
- [ ] Services
- [ ] Scheduled tasks
- [ ] Writable service paths
- [ ] Unquoted service paths
- [ ] Writable directories
- [ ] Registry
- [ ] Run keys
- [ ] Installed software
- [ ] Environment variables
- [ ] Credentials
- [ ] PowerShell history
- [ ] Shares
- [ ] Security controls

## 18.4 Web Checklist

- [ ] Technology fingerprinting
- [ ] Headers
- [ ] Cookies
- [ ] Directories
- [ ] Files
- [ ] Backups
- [ ] Parameters
- [ ] Virtual hosts
- [ ] Authentication
- [ ] Authorization
- [ ] SQLi
- [ ] XSS
- [ ] Traversal
- [ ] File inclusion
- [ ] File upload
- [ ] Command injection
- [ ] SSRF
- [ ] API endpoints
- [ ] Source review
- [ ] JavaScript review

## 18.5 AD Checklist

- [ ] Domain
- [ ] Domain controllers
- [ ] Users
- [ ] Groups
- [ ] Computers
- [ ] Shares
- [ ] LDAP
- [ ] SMB
- [ ] SPNs
- [ ] Kerberos
- [ ] AS-REP exposure
- [ ] Kerberoasting exposure
- [ ] Password policy
- [ ] Trusts
- [ ] ACLs
- [ ] Delegation
- [ ] GPOs
- [ ] Local administrators
- [ ] Sessions
- [ ] Credential material
- [ ] Attack paths

## 18.6 Reporting Checklist

- [ ] Scope
- [ ] Executive summary
- [ ] Attack narrative
- [ ] Finding titles
- [ ] Severity
- [ ] Affected systems
- [ ] Technical description
- [ ] Reproduction
- [ ] Evidence
- [ ] Impact
- [ ] Remediation
- [ ] References
- [ ] Proof/flags where applicable
- [ ] Screenshots
- [ ] Final proofreading

# 19 — Note-Taking System

Use one directory per target:

```text
target/
├── recon/
│   ├── tcp/
│   ├── udp/
│   ├── dns/
│   ├── smb/
│   └── web/
├── loot/
├── credentials/
├── exploits/
├── privesc/
├── pivot/
├── evidence/
└── report/
```

## Target Notes Template

```text
Target:
IP:
Hostname:
OS:
Domain:

OPEN PORTS
----------

SERVICE ENUMERATION
-------------------

INITIAL ACCESS
-------------

CREDENTIALS
-----------

LOCAL ENUMERATION
-----------------

PRIVILEGE ESCALATION
--------------------

PIVOTING
--------

LATERAL MOVEMENT
----------------

PROOF
-----

FAILED APPROACHES
-----------------

LESSONS LEARNED
---------------
```

# 20 — Lab Architecture

## 20.1 Minimum Lab Components

Recommended isolated environment:

```text
                Attack VM
                    |
             Lab Network
                    |
        +-----------+-----------+
        |                       |
     Linux Host             Windows Host
        |                       |
        +-----------+-----------+
                    |
              AD Environment
             /       |       \
           DC      Server   Workstation
```

## 20.2 Lab Goals

Build scenarios covering:

- Misconfigured services
- Vulnerable web applications
- Linux privilege escalation
- Windows privilege escalation
- Credential reuse
- SMB
- LDAP
- Kerberos
- AD ACLs
- Delegation
- Pivoting
- Multiple subnets
- Reporting

## 20.3 Safety

- Use host-only/internal networking where possible.
- Do not expose vulnerable machines to the public Internet.
- Snapshot machines before experiments.
- Keep credentials synthetic.
- Maintain a clean reset state.

# 21 — Study Plan

## Phase 1 — Foundations

### Week 1

- Networking
- Linux
- Windows
- Bash
- PowerShell
- Python
- HTTP

### Week 2

- Nmap
- Service enumeration
- DNS
- SMB
- FTP
- SSH
- SMTP
- SNMP
- LDAP
- RDP
- WinRM

## Phase 2 — Web and Exploitation

### Week 3

- Web enumeration
- Authentication
- Authorization
- SQL injection
- XSS
- Traversal
- File inclusion
- File upload
- Command injection

### Week 4

- Public exploit research
- PoC analysis
- PoC modification
- Payloads
- Shell stabilization
- Exploitation troubleshooting

## Phase 3 — Privilege Escalation

### Week 5

- Linux enumeration
- sudo
- SUID/SGID
- capabilities
- cron
- services
- filesystem permissions
- credentials

### Week 6

- Windows enumeration
- services
- scheduled tasks
- registry
- tokens
- privileges
- credentials
- application weaknesses

## Phase 4 — Active Directory

### Week 7

- AD architecture
- LDAP
- SMB
- domain enumeration
- users/groups/computers
- Kerberos
- NTLM

### Week 8

- Kerberoasting
- AS-REP roasting
- ACLs
- delegation
- GPOs
- trusts
- attack graphs
- lateral movement

## Phase 5 — Pivoting and Integration

### Week 9

- Routing
- tunnels
- SOCKS
- port forwarding
- multi-hop pivoting
- internal enumeration

### Week 10

- Full attack chains
- Mixed Windows/Linux targets
- AD attack paths
- Timeboxed machines

## Phase 6 — Exam Simulation

### Week 11

- Full timed practice
- Minimal external references
- Complete evidence collection
- Complete report

### Week 12

- Second full simulation
- Weak-area remediation
- Reporting drill
- Final checklists
- Exam workflow rehearsal

Adjust this schedule to your starting skill level and the current official course/exam requirements.

# 22 — Completion Criteria

You are ready for an exam-style attempt when you can consistently:

## Enumeration

- [ ] Perform systematic host/service enumeration without a tutorial.
- [ ] Identify the most promising attack surfaces.
- [ ] Explain why a finding matters.

## Exploitation

- [ ] Research public exploits efficiently.
- [ ] Read and modify a PoC.
- [ ] Troubleshoot exploit failures methodically.
- [ ] Obtain and stabilize a shell in a controlled lab.

## Privilege Escalation

- [ ] Enumerate Linux hosts manually.
- [ ] Enumerate Windows hosts manually.
- [ ] Identify common permission/configuration weaknesses.
- [ ] Explain why an escalation path works.

## Active Directory

- [ ] Explain AD authentication.
- [ ] Enumerate users/groups/computers.
- [ ] Identify Kerberos attack opportunities.
- [ ] Analyze ACLs.
- [ ] Reason about delegation.
- [ ] Build an attack path from graph relationships.

## Pivoting

- [ ] Identify routes/interfaces.
- [ ] Establish a tunnel.
- [ ] Reach an internal service.
- [ ] Enumerate through a pivot.

## Reporting

- [ ] Reconstruct the entire attack chain from notes.
- [ ] Provide clear evidence.
- [ ] Explain impact.
- [ ] Provide actionable remediation.
- [ ] Produce a professional report under time pressure.

# 23 — References

Use authoritative documentation first and treat third-party writeups as supplementary learning material.

## Official / Primary

- OffSec PEN-200: https://www.offsec.com/courses/pen-200/
- OffSec Help Center: https://help.offsec.com/
- OffSec OSCP+ information: https://www.offsec.com/courses/certifications/oscp/

## Networking

- Nmap Reference Guide: https://nmap.org/book/man.html
- RFC Editor: https://www.rfc-editor.org/

## Web Security

- OWASP Web Security Testing Guide: https://owasp.org/www-project-web-security-testing-guide/
- OWASP Top 10: https://owasp.org/www-project-top-ten/

## Vulnerability Research

- NIST NVD: https://nvd.nist.gov/
- MITRE CVE: https://cve.org/
- MITRE CWE: https://cwe.mitre.org/

## Adversary Knowledge

- MITRE ATT&CK: https://attack.mitre.org/

## Windows

- Microsoft Learn: https://learn.microsoft.com/

## Linux

- Linux man-pages: https://man7.org/linux/man-pages/

# Final Principle

The objective is not to memorize an enormous command list.

The objective is to develop a reliable decision-making loop:

```text
ENUMERATE
    ↓
UNDERSTAND
    ↓
HYPOTHESIZE
    ↓
VALIDATE
    ↓
EXPLOIT
    ↓
ENUMERATE AGAIN
    ↓
ESCALATE
    ↓
PIVOT / MOVE
    ↓
PROVE
    ↓
DOCUMENT
```

A strong OSCP+ practitioner can explain **why** a path works, reproduce it from their notes, recover when it fails, and communicate the complete security impact clearly.
