# Website inquiry follow-up (n8n)

When someone fills in a website contact form, this n8n workflow saves the inquiry, emails the owner, and sends the visitor an instant reply (English and Malay).

![status](https://img.shields.io/badge/status-demo-blue)

## What it does

1. A webhook receives the form POST.
2. A code node checks the fields (name, valid email, message) and drops bot submissions through a hidden honeypot field.
3. The inquiry is saved as a row. In this demo it goes to an n8n Data table. In a real build it goes to a Google Sheet.
4. The owner gets an email alert.
5. The visitor gets an automatic reply.
6. The webhook answers `200` with JSON.

A 56-second screen recording is in [`demo.mp4`](demo.mp4). It uses a fictional business ("Demo Dental KL") and a local test inbox, not Gmail.

## Use it

1. In n8n, choose **Import from file** and pick `inquiry-follow-up.workflow.json`.
2. Create an SMTP credential and select it on both email nodes.
3. Create a Data table named `demo_inquiries` with columns that match the code node's output, or swap that node for Google Sheets.
4. Change `owner@example.com` to the owner's address.
5. Point your form at the webhook URL, with path `oqvian-demo-inquiry-follow-up`.

## Limits

- This is a demo, not client work. No credentials are included.
- The Data table stands in for Google Sheets.
- It does not retry failed emails and has no spam filter beyond the honeypot.

## Want this on your site?

OQVIAN builds this for a fixed $300, delivered in 4 working days, with one revision and 14 days of bug fixes: https://www.oqviangroup.com/offer
