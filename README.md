# ITGC Access Audit - Project 

Built this to test whether a company's user access controls actually hold up — the kind of 
check an IT auditor runs before a SOX or ISO audit.

## What it does

Simulated a mid-size company's access data: 50 employees, 5 systems (ERP, HR/Payroll, Active 
Directory, CRM, a banking portal), 174 access grants, plus HR termination records and 
recertification logs. Then built out formulas to test four things:

- Did terminated employees actually lose access within the required 5-day window?
- Does anyone hold two roles that shouldn't be combined (like entering AND approving the same 
  payment)?
- Was every access grant properly approved and documented?
- Is privileged/admin access getting reviewed on schedule?

## Result

78 out of 174 access grants (about 45%) failed at least one of these checks. The failures 
weren't random either — they were concentrated in Accounts Payable, Payroll, and Treasury, 
which are exactly the areas where this kind of gap matters most.

## How it's built

Everything is plain Excel formulas — INDEX/MATCH, COUNTIFS, nested IF statements. No VBA, no 
macros, no black-box scoring. Every flag in the workbook traces back to a formula you can open 
and read.

## Files

- `ITGC_Access_Audit.xlsx` — the full workbook: source data, the testing logic, a dashboard, 
  and a written findings memo.
