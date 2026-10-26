# Functional Escalation: Check Scanner Batch Upload Failure

**Who did I escalate to?** I escalated this to the scanner vendor’s tier 3 engineering team.

**Why did this exceed what I could resolve myself?** Everything on our side tested clean, and the evidence points to the vendor’s server timing out on larger batches. I can’t see or change anything on their system, so the vendor has to investigate and fix it.

---

## Escalation Note

Escalating to the vendor's tier-3 engineering team.

**Issue:** The Panini Vision X check scanner at Elm Street keeps failing on larger batch uploads with ERR_BATCH_TIMEOUT_504.

**Impact:** Elm Street can't reliably process deposits. The head teller has been driving checks about 9 miles to another branch every afternoon for three weeks. That slows down customers' funds and puts their checks at risk on the road.

**What I tried and what happened:**

- Ran the local diagnostic tool. The scanner passed its self-test.
- Scanned 3 checks. The batch uploaded fine.
- Ran a simulated 25-check batch in staging. It timed out at check 18.
- Cleared the cache, updated the driver from v5.2.1 to v5.2.3, and plugged in directly by Ethernet. A 20-check batch worked once, then failed with the same error the second time.

**What I ruled out:** The scanner itself, the USB connection, the driver, and our local network. Small batches of 1 to 3 checks always go through. It only fails on bigger ones.

**What I need from you:** Can you check your server logs for timeouts on batch uploads from our account, let us know if there's a batch size or timeout limit we're hitting, and give us a timeline for a fix? Our teller is logging the time, check count, and error message every time it fails again, and I'll send those over as they come in.
