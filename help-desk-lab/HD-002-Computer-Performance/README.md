# HD-002 — Windows 11 Performance Troubleshooting

## Project Overview

This lab demonstrates foundational Windows 11 performance troubleshooting using built-in system administration tools.

## Business Scenario

A fictional Northstar Solutions employee reports that their Windows 11 workstation is running slowly.

Applications reportedly take longer than expected to open, and the computer occasionally freezes.

## Objective

Investigate possible causes of slow computer performance and document the findings.

## Tools Used

- Windows 11
- Task Manager
- Windows Settings
- GitHub Issues
- Snipping Tool

## Troubleshooting Performed

### 1. CPU and Memory Investigation

Used Windows Task Manager to examine CPU, memory, and disk utilization.

Initial observations:

- CPU: 9%
- Memory: 70%
- Disk: 0%

### 2. Memory Investigation

Sorted running processes by memory consumption.

Top applications:

| Application | Memory Usage |
|---|---|
| Google Chrome | 825.0 MB |
| ChatGPT Classic | 729.7 MB |
| Start | 190.2 MB |

Total memory utilization during this investigation was approximately 69%.

### 3. Startup Application Investigation

Reviewed startup applications using Windows Task Manager.

Identified 11 visible startup applications configured as Enabled.

Startup impact was displayed as Not measured.

No applications were disabled.

### 4. Storage Investigation

Reviewed Windows 11 storage information.

| Measurement | Result |
|---|---|
| Total Storage | 934 GB |
| Used Storage | 486 GB |
| Available Storage | 448 GB |
| Installed Applications | 270 GB |
| Temporary Files | 34.3 GB |

The computer had approximately 48% free storage space.

### 5. CPU Performance Investigation

Reviewed the CPU Performance section in Task Manager.

Results:

- CPU utilization: 12%
- CPU speed: 2.43 GHz
- Processes: 324
- Threads: 5,906

## Findings

- CPU utilization was relatively low during the investigation.
- Memory utilization was approximately 69–70%.
- Multiple applications were configured to start automatically.
- Available storage was sufficient.
- No major performance bottleneck was confirmed during the observations.

## Outcome

Completed a non-disruptive Windows 11 performance investigation.

The computer used for testing was functioning normally.

The fictional employee's performance problem was not reproduced or resolved.

## Skills Demonstrated

- Windows performance monitoring
- Task Manager
- Process investigation
- Startup application review
- Storage analysis
- Technical documentation
- Help Desk ticket management

## Evidence

Screenshots and a detailed troubleshooting report will be added to this project.

## Disclaimer

This is an educational lab using a fictional company and employee scenario.
