Here's a full README for your EMI Calculator:

---

# 🇮🇳 Bharat EMI Calculator

A beautiful, fully offline, single-file HTML EMI Calculator built for Indian users with 20+ banks, loan application form, prepayment planner, and amortization schedule.

---

## 🚀 How to Use

1. Download the file `emi-calculator-india.html`
2. Open it in any browser (Chrome, Firefox, Edge, Safari)
3. No internet needed — works 100% offline
4. No installation, no dependencies, no server required

---

## ✨ Features

### 🏦 20+ Indian Banks Covered

**PSU Banks** — SBI, PNB, Bank of Baroda, Bank of India, Canara Bank, Union Bank, Indian Bank, Central Bank of India, UCO Bank, IOB

**Private Banks** — HDFC Bank, ICICI Bank, Axis Bank, Kotak Mahindra, Yes Bank, IDFC First, IndusInd Bank, Federal Bank

**NBFCs / HFCs** — LIC Housing Finance, HDFC Ltd, Bajaj Finserv, Tata Capital

---

### 🏠 6 Loan Types
| Type | Default Amount | Default Tenure | Default Rate |
|------|---------------|----------------|--------------|
| Home Loan | ₹30,00,000 | 20 years | 8.50% |
| Car Loan | ₹8,00,000 | 7 years | 9.00% |
| Personal Loan | ₹5,00,000 | 5 years | 11.00% |
| Education Loan | ₹10,00,000 | 10 years | 8.65% |
| Gold Loan | ₹2,00,000 | 2 years | 7.50% |
| Business Loan | ₹20,00,000 | 5 years | 9.50% |

---

### 📊 5 Tabs

**1. Overview Tab**
- Donut chart showing Principal vs Interest vs Fees split
- Principal : Interest ratio
- Cost of credit percentage
- First month interest amount
- Break-even month (when principal repaid exceeds interest paid)

**2. Banks Tab**
- All 20+ banks listed with their current rates
- Search bar to find any bank instantly
- Filter by PSU / Private / NBFC
- Sort by Bank Name, Interest Rate, or EMI amount
- EMI bar chart comparing all banks visually
- "Best Rate" badge on cheapest option
- Extra cost per month shown vs best bank
- One-click Apply button that pre-fills the bank in the application form

**3. Amortization Schedule Tab**
- Yearly view — see year-by-year breakdown
- Monthly view — first 24 months detailed
- Quarterly view — quarter-by-quarter summary
- Progress bar showing % of loan repaid
- Grand total row at the bottom

**4. Prepayment Planner Tab**
- Add multiple lump-sum prepayments at any month
- Instantly see how many months you save
- Total interest saved shown in ₹
- New effective tenure after prepayments
- Effective return on your prepayment calculated

**5. Apply Now Tab**
- Full loan application form
- Real-time eligibility score (0–100%) as you type
- Fields: Name, DOB, PAN, Aadhaar, Mobile, Email
- Employment type, monthly income, existing EMIs
- CIBIL score selector with impact shown
- Work experience, state, preferred bank, rate type
- Property/collateral address
- FOIR (Fixed Obligation to Income Ratio) check
- PAN format validation (ABCDE1234F)
- 10-digit mobile validation
- Submit shows confirmation toast

---

### ⚙️ Input Controls

| Control | Range |
|---------|-------|
| Loan Amount (slider) | ₹50,000 – ₹1 Crore |
| Tenure (slider) | 1 – 30 years |
| Interest Rate (slider) | 5% – 24% |
| Direct number input | Principal, Rate, Years, Months |
| Down Payment | Any amount |
| Processing Fee | % of loan |
| Insurance | ₹ per year |
| Repayment Frequency | Monthly / Quarterly / Half-Yearly / Yearly |

---

## 🛠️ Technical Details

- **Single file** — everything in one `.html` file
- **Zero dependencies** — no Bootstrap, no jQuery, no npm
- **Offline ready** — works without internet (fonts load from Google Fonts if online, fallback to system font if offline)
- **Responsive** — works on mobile, tablet, desktop
- **EMI Formula used:**

```
EMI = P × R × (1+R)^N / [(1+R)^N – 1]

Where:
  P = Principal (loan amount – down payment)
  R = Monthly interest rate (annual rate ÷ 12 ÷ 100)
  N = Total months (years × 12)
```

---

## 📁 File Structure

```
emi-calculator-india.html   ← The entire app (single file)
```

---

## 🔧 How to Customize

**Add a new bank** — find the `BANKS` array in the `<script>` tag and add an entry:
```js
{
  name: "My Bank",
  short: "MB",
  type: "public",            // public / private / nbfc
  rate: { home:8.6, car:9.0, personal:11.5, education:8.7, gold:7.5, business:9.8 },
  fee:  { home:"0.5%", car:"0.5%", personal:"1%", education:"0%", gold:"0%", business:"1%" },
  badge: ""                  // "pop" = Popular, "pvt" = Private, "" = none
}
```

**Change loan amount range** — edit `min` and `max` on `id="r-amt"`

**Change default values** — edit the `defaults` object inside `setType()`

---

## ⚠️ Disclaimer

Interest rates shown are indicative and based on publicly available data. Actual rates may vary by bank, applicant profile, and RBI policy changes. Always confirm current rates directly with the bank before applying.

---

## 👨‍💻 Built With

- Vanilla HTML + CSS + JavaScript
- Google Fonts — Playfair Display + Outfit
- HTML5 Canvas (donut chart)
- No frameworks, no libraries