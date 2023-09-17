# Threat Modeling

### Identify Threats
- Focus on Assets
- Focus on Attackers
- Focus on Software

### Determine and Diagram Potential Attacks
- Create flow diagrams to see how users interact with your application
- Identify attacks on each element of the diagram

### Perform Reduction Analysis
Decompose the application to understand the logic behind how each piece interacts with each other. 

Identify these 5 key concepts: 
- Trust boundaries: where does trust or security change
- Data flow paths: how does data move in the application
- Input points: Where does external input get processed
- Privileged Operations: Where are greater privileges required
- Details about Security Stance and approach: look at the security policies and design documents

### Prioritization and Response
Rank or rate the threats. A common way is:  
```
probability * damage potential Ranking (High/Med/Low)
```


