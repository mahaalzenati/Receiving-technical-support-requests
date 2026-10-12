# IT Support Automation – CTCO Prompt Structure

## 1. Trigger
- Employee submits an IT support request through a form.
- The automation starts when a new form response is received.

## 2. Inputs
- `employee_name`
- `employee_email`
- `department`
- `problem_description`
- `submission_date`

## 3. Unstructured Data
- `problem_description`
- Free-text description of the technical issue reported by the employee.
- May include symptoms, error messages, affected systems, and business impact.

## 4. Structured Data
- `problem_summary`
- `problem_type`
- `priority`

## 5. Data Schema

| Field | Data Type | Allowed Values |
|---|---|---|
| `problem_summary` | String / Null | Concise problem summary |
| `problem_type` | String | `hardware`, `software`, `network`, `email`, `account_access`, `permissions`, `printer`, `security`, `other`, `unclear` |
| `priority` | String | `critical`, `high`, `medium`, `low`, `needs_review` |

## 6. Missing Information
- Identify information that is missing, ambiguous, or insufficient to classify the issue reliably.
- Never invent, assume, or guess missing information.
- Do not infer the root cause of the problem.
- Use `null` when the problem description is missing or no actual problem is described.
- Use `unclear` when the problem type cannot be determined.
- Use `needs_review` when there is insufficient evidence to assign a reliable priority.

## 7. Validation
- Return only valid JSON.
- Include exactly the three required output fields:
  - `problem_summary`
  - `problem_type`
  - `priority`
- Use only the allowed values defined in the data schema.
- Ensure `problem_summary` contains only explicitly reported facts.
- Never assign priority based on urgency wording alone.
- Do not add explanations, Markdown, or extra fields to the JSON output.
- Route ambiguous or high-risk cases for human review according to the company's support policy.
