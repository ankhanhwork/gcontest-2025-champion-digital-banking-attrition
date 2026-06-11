# Business Recommendations

## Prioritization Principle

The bank should concentrate resources where failure volume and recoverability
are both high. OCR and OTP together represented approximately 80% of observed
failures, making them the first intervention candidates.

## 1. Improve OCR Recovery

### Product changes

- Check camera permission, lighting, glare, blur, and document framing before
  submission.
- Provide real-time visual guidance instead of a generic rejection message.
- Preserve captured information when a retry is required.
- Offer a clearly visible assisted verification path after repeated failures.

### Success measures

- OCR failure rate;
- successful recovery after the first OCR error;
- average OCR attempts per successful customer;
- abandonment immediately after OCR.

## 2. Strengthen OTP Reliability

### Product changes

- Display phone-number confirmation before sending the code.
- Make expiry time, resend availability, and remaining attempts explicit.
- Distinguish wrong-code, expired-code, delivery, and network errors.
- Provide an alternative verification or support route after repeated
  delivery failures.

### Success measures

- OTP delivery and verification rate;
- median verification time;
- resend frequency;
- abandonment following an OTP error.

## 3. Detect Device Compatibility Early

### Product changes

- Run a preflight check for OS version, camera capability, and NFC support.
- Warn customers before they reach a step their device cannot complete.
- Provide a supported-device list and practical alternatives, such as
  continuing on another device or using an assisted channel.

### Success measures

- failure rate by device and OS version;
- completion after a compatibility warning;
- support usage and alternative-channel conversion.

## 4. Design For Older Customers

### Product changes

- Use clearer language, larger interaction targets, and step-by-step
  explanations.
- Provide contextual help at OCR, OTP, privacy consent, and contract steps.
- Trigger optional human support after repeated failed attempts.

### Success measures

- completion and recovery rates by age cohort;
- support-assisted completion;
- time and attempts required to complete onboarding.

## 5. Preserve Progress And Motivation

### Product changes

- Save progress securely and let customers resume at the correct step.
- Explain the remaining effort and benefit of completing the application.
- Test targeted incentives for customers who abandon after a recoverable
  error.

### Success measures

- resume-to-completion rate;
- first-error abandonment rate;
- incremental completion from incentives;
- acquisition cost per successfully onboarded customer.

## 6. Rollout And Measurement

1. Instrument each onboarding event with consistent error taxonomy.
2. Establish baseline funnel metrics by cohort and device.
3. Pilot OCR and OTP improvements first.
4. Use randomized or phased experiments where operationally possible.
5. Track completion, recovery, time, complaints, fraud, and support load
   together.
6. Scale only changes that produce sustained improvement without weakening
   compliance or risk controls.

The proposal estimated that a successful redesign could raise completion from
93% toward 97%. This should be treated as an ambition to test, not a guaranteed
forecast.
