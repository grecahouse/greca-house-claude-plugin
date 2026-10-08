---
type: llm
---

PASS if the total either comes from a search with max_price_eur 299999, or clearly says it includes listings priced exactly €300,000 ("up to" or "€300,000 or less") and how many are at the cap. FAIL if a count from max_price_eur=300000 is presented as strictly under €300,000, if the answer never states which regions or area the total covers, or if any stated part is larger than its whole.
