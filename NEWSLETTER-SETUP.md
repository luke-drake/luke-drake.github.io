# Connecting the newsletter (Kit, free plan)

The site is already wired for Kit. After the steps below, the only site change is two lines in `hugo.toml`:

```toml
  [params.newsletter]
    provider = "kit"
    form_id = "1234567"   # your number
```

## What Luke provides
- **Account email.** The address that owns the Kit account. A personal address is safest. See "Sender address" below.
- **Password.** Generate and store it in the vault. Never paste it in chat.
- **Verification code or link.** Kit emails this to the account address at signup.
- **Newsletter name.** Suggestion: "Come, Follow Me with Luke Drake" or "The World of the New Testament".
- **From name and sender address.** For example "Luke Drake" and the address readers see.
- **Postal mailing address.** The law (CAN-SPAM) requires one in every email footer. It can be a PO box or office address.
- **The free study PDF** (optional, can be added later). It's delivered by the confirmation email.

## Sign-up steps (for a browser helper)
1. Open https://app.kit.com/users/signup (or https://kit.com/pricing → Free plan → "Get started").
2. Enter Luke's **email** and a **vault-generated password**. Submit.
3. Answer the onboarding questions (creator type: "Writer/Author"; list size: "0 / starting out"). If asked to pick a plan, choose **Free** and skip any trial or card prompt.
4. Enter the **verification code** from Kit's email, or click the link in it.
5. Go to **Settings → Account** (or **Settings → Email**). Fill in:
   - **From name:** Luke Drake
   - **Sender email:** the chosen address. Kit sends a confirmation link; click it.
   - **Physical address:** Luke's mailing address
6. Go to **Settings → Creator Network (Recommendations)** and turn recommendations **off** if Luke doesn't want other newsletters suggested to his sign-ups. Kit's Free-plan help says this is optional.
7. Create the form: **Grow → Landing Pages & Forms → + Create new → Form → Inline**, any template. Name it "Website sign-up".
8. In the form builder, open **Settings**:
   - **General → After subscribing:** "Redirect to an external page" → `https://<site-domain>/thanks/`. Or leave it on "Show a success message".
   - **Confirmation email:** keep **Send confirmation email** checked and **Auto-confirm** unchecked (this is double opt-in). Edit the email text.
   - **After confirming, redirect to:** choose **Download** and upload the study PDF. Keep the filename under 20 characters with no spaces, for example `CFM2027-guide.pdf`. Or set a URL.
   - Click **Save**, then **Publish**.
9. **Get the form ID:** click **Embed → HTML**. The code contains `action="https://app.kit.com/forms/1234567/subscriptions"`. The number is the form ID. It is also in the browser URL while editing the form.
10. Put that number in `hugo.toml` as `form_id`, set `provider = "kit"`, and rebuild.
11. Test it: sign up on the site with a test address, confirm, and check that the PDF downloads. Then delete the test subscriber.

Optional: **Grow → Creator Profile** turns on a public archive of past emails at `<name>.kit.com`. When sending each broadcast, tick "Publish to Creator Profile".

## Sender address
- BYU's mail domain publishes a DMARC policy of `p=quarantine` (checked Oct 27, 2026).
- Bulk mail sent "From: lukedrake@byu.edu" through Kit would fail that check unless BYU IT adds Kit's DNS records, so it would probably land in spam.
- Better: a personal address on a domain Luke owns (for example, the site's future domain), verified in Kit under Settings → Email → Verified Sending Domain.
- lukedrake@byu.edu can still be the public contact or reply-to.
