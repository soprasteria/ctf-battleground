# CTF Battleground

Capture The Flag Battleground aim to have real infrastructure environment on which 2 teams fights one to attack (Red Team) the infrastructure and one to detect (Bleu Team) the attacks.


## Chapters

### Chapter 1: Raise to the cloud

First session of CTF Battleground Wednesday 22th November 2018.
The Battleground will be generated on Amazon AWS, the SIEM will be Splunk Enterprise.

[Read the story](chapter1)

## Infrastructure Team
The infrastructure team is in charge to generate the battleground which is an infrastructure for the battle.
This infrastructure must push all the data to a SIEM for the defense part (Blue Team).
This infrastructure must have vulnerabilities for the attack part (Red Team).
This infrastructure must be functional with endpoint/entrypoint exposed on internet.
Infrastructure team provides Architecture details and Security setup to the Blue Team.
Infrastructure team provides Objectives to the Red Team (find and leak data, destroy target, Take control of an account ...) that are not known by the Blue Team.

## Bleu Team
Bleu team is in charge to analyse data in the SIEM to detect and investigate (potentially respond in the future) to attacks on going.
Blue team must write findings summary and store evidences of their detections and investigations.


## Red Team
Red Team is in charge to attack the infrastructure to take control of the infrastructure.
Red team must write findings summary and store evidences of their attacks with results.

## Rules
1. You do talk about CTF Battleground
2. You do talk about CTF Battleground
3. DNS Walking is prohibited (from AWS rules)
4. You do not touch the Log Collector (Universal Log Forwarder) on the challenge's instances
5. You do not touch ~/.ssh/authorized_keys
6. You never ever get out of the subnet given
7. You catch a flag you raise your hands and store evidences (Screenshots, Logs, Dump, Flag key string)
8. Reds universal flag is to get root or administrator privileges
9. Blues universal flags are attacks discovering
10. Reds have secrets flags to catch
11. Blues know their infrastructure to watch but not the challenges
12. Reds activity is not always an attack (so a flag)
13. Reds attack furtivity is score factor for them
14. Blues discovered attack complexity is score factor for them
15. Blues can perform forensic on machines only to gather data (no trap allowed)

## Scoring
1. each flag is 1 point
 1. For Red it is a flag catched
 2. For Blue is a sequence of log showing Red attack on a machine (Successful or not)
 3. Bonus Flag of the battleground is x10 (if catched by Red, Discovered attack related by Blue)
2. multiplicators
 1. For red
  1. if it is not a machine exposed on public ip adresse x2
  2. If attack is not discovered by Blue team x3
  3. If attack is partially discovered by Blue Team x2
  4. if there is a sequenced attack across machines x Nb machines not discovered
 3. For blue
  1. if there is a sequenced attack across machines x Nb machines discovered
  3. if reverse (crypto, binary, obfuscated code) has been done to uncover the attack x2
  4. if forensic has been done with findings x3
  5. if markers has been setuped in the SIEM and could trigger the attack identified x2 (IP addresses is excluded)

