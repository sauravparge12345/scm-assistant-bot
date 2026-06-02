# Supply Chain Management Assistant Chatbot
## Public Chatbot URL
https://cloud.flowiseai.com/chatbot/76390f17-df4c-44c1-b00e-905a9384c8cf

## Technical Architecture
- **LLM Used:** gemini-2.5-flash
- **Embeddings Model Used:** gemini-embedding-001

## Chunk Configuration Experiments
- **Chunk Size of csv file:** 2000
- **Chunk Overlap of csv file:** 200
- **Resulting Chunk Count:** 2000

- **Chunk Size of pdf file:** 500
- **Chunk Overlap of pdf file:** 50
- **Resulting Chunk Count:** 35

## Sample Q&A

1) Which Tier-3 suppliers have an active disruption flag, and what response level applies per policy?

AI
The following 11 Tier-3 suppliers have active disruption flags:
Dravex Components India
Plataforma Metales SA
Maghreb Castworks
Helios Pack Greece
Cerromax Mineria
Orinoco Pack SAPI
Quetzal Textiles
Sibertek Molding
Archipelago PCB Corp
Varna Electronics EAD
Deltaforge Vietnam
Per Policy §9, these suppliers trigger a Level 3 Activate response, which requires CPO escalation and securing an alternate supplier for a minimum of 40% of the volume.

Me
2) Which suppliers qualify for the annual Volume Rebate Program and how many are there?

AI
There are 19 suppliers that qualify for the annual Volume Rebate Program.
They are:
Borealis Composites
Crestline Chemical Supply
Fenwick Alloy Solutions
Hanguk Circuit Works
Hokkaido Alloy Tech
Krauss-Polymex GmbH
Lakeshore Components
Lumivex Semiconductor NL
Maplewood Polymer Corp
Norbec Alloy Works
Nordloom Finland Oy
Orrentek Precision Mfg
Ostwind Composites AG
Precision Forge Taiyuan
Solveig Eco Packaging
Straits Packaging Hub
Tasman Circuit Boards
Toreval Electronics
Valdoro Special Alloys

Me
3) Which region has the highest total PO value, and does it breach the concentration limit?

AI
EMEA has the highest total PO value at $193,987,179.91, which represents approximately 48.5% of the total spend.
Yes, this breaches the 45% regional concentration cap as defined in Policy §5.3. A Diversification Plan is required within 60 days due to this breach.

Me
4) Which suppliers are on Supplier Watch List (SWL) status and what does it restrict?

AI
The following 11 suppliers are on the Supplier Watch List (SWL) status because their Compliance Score is below 60:
Deltaforge Vietnam
Maghreb Castworks
Helios Pack Greece
Cerromax Mineria
Orinoco Pack SAPI
Varna Electronics EAD
Quetzal Textiles
Plataforma Metales SA
Archipelago PCB Corp
Dravex Components India
Sibertek Molding
Per Policy §3.4, being on the SWL restricts new Purchase Order (PO) issuance to 20% of their prior quarter volume.

Screenshots
<img width="1731" height="1033" alt="Screenshot 2026-06-02 143946" src="https://github.com/user-attachments/assets/f5635991-6148-4c70-88fb-7e4dc140189a" />
<img width="1918" height="1073" alt="Screenshot 2026-06-02 142340" src="https://github.com/user-attachments/assets/277b3b70-7b8b-4f04-a3ac-92706a1a9777" />
<img width="1917" height="1026" alt="Screenshot 2026-06-02 133514" src="https://github.com/user-attachments/assets/f5d5e691-f57c-45e0-bd63-960f327335a0" />
<img width="1918" height="1098" alt="Screenshot 2026-06-02 111827" src="https://github.com/user-attachments/assets/37528be9-1e53-4c37-8a5f-cad8523655f6" />
<img width="1918" height="1078" alt="Screenshot 2026-06-02 102817" src="https://github.com/user-attachments/assets/3d16098d-9955-4870-93a7-4e080747eeb3" />
<img width="1918" height="1067" alt="Screenshot 2026-06-02 101859" src="https://github.com/user-attachments/assets/16618fb3-4a0b-4598-9095-185dfe6ca081" />
<img width="1913" height="1017" alt="Screenshot 2026-06-02 100856" src="https://github.com/user-attachments/assets/35cd6355-5939-4420-92a5-9f5ac5818565" />
<img width="1916" height="995" alt="Screenshot 2026-06-02 100054" src="https://github.com/user-attachments/assets/ae2dcca8-c8c1-4a00-bc04-7d9b0aaa4b6a" />
<img width="1913" height="997" alt="Screenshot 2026-06-02 095816" src="https://github.com/user-attachments/assets/dd84787f-54eb-4480-b37e-a678a57f0ef9" />

### Problems:
During the development of the `SCM Assistant` chatbot, a technical bottleneck was encountered when attempting to index the `supplier_performance_data.csv` file directly into the Document Store vector database (Pinecone) via Flowise.


### What I Would Improve Next Time:
Instead of using a standard Document Store vector loader for large CSVs, I would write a quick Python preprocessing script to convert each row of the CSV into a semantic sentence or leverage a dedicated SQL/Pandas Agent node inside Flowise to query the structured CSV file directly via code execution rather than vector semantic search. 
I have done Ollama-Movies-Recommendation-Chatbot project 
-https://github.com/sauravparge12345/Ollama-Movies-Recommendation-Chatbot
