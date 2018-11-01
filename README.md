fauxmailer
=============================================================================
[![Build Status](https://travis-ci.org/jhillyerd/fauxmailer.svg?branch=master)](https://travis-ci.org/jhillyerd/fauxmailer)

fauxmailer will generate random emails, and send them via SMTP.

The initial goal for this project is to populate a demo instance of
[Inbucket].

## Usage

    Usage of fauxmailer:
      -every duration
            sends a message every <duration> if non-zero
      -host string
            host:port of SMTP server (default "localhost:25")
      -signature string
            signature (default "Generated by https://github.com/jhillyerd/fauxmailer")
      -silent
            disable to/from address log
      -tofile string
            optional file containing newline separated To addresses
      -verbose
            enable verbose output

### Examples

To send a single message to a random address via your local mail server:

    fauxmailer -verbose

To send about four messages per second to your local Inbucket server:

    fauxmailer -host localhost:2500 -every 250ms

To send a message every five minutes to a random address selected from the
contents of `addresses.txt`:

    fauxmailer -host exchange.mycorp:25 -tofile addresses.txt -every 5m

### Sample Output

Example of fauxmailer output with `-verbose` flag:

    2018/11/01 13:55:16 jakob@powlowskihowell.net -> pansy@pouros.info
    2018/11/01 13:55:16 Sending:
    Content-Type: multipart/alternative;
     boundary=enmime-389602d4-f07c-413e-a30c-2b48e73db32f
    Date: Thu, 01 Nov 2018 13:55:16 -0700
    From: <jakob@powlowskihowell.net>
    Mime-Version: 1.0
    Subject: Engineer Proactive E-Business with Beer, Weissnat and Boyle
    To: <pansy@pouros.info>

    --enmime-389602d4-f07c-413e-a30c-2b48e73db32f
    Content-Type: text/plain; charset=utf-8

    Aut sequi illo qui vacuus. Sint bellicus blanditiis. Laboriosam congregatio ab laborum ars.

    Degero vigilo contra varietas qui occaecati debeo. Tempora animi appello ad est. Et ipsum desipio asper.

    Centum similique consequatur eos. Vitae bestia qui enim. Aedificium labore nostrum solio.

    Facilis ubi calculus dolorum. Et aer usus aut quod vulgo adnuo nesciunt. Thalassinus cumque voluptatem culpa.

    Brain Considine <jakob@powlowskihowell.net>, Direct Assurance Executive
    Beer, Weissnat and Boyle, "Sharable incremental synergy"

    --
    Generated by https://github.com/jhillyerd/fauxmailer

    --enmime-389602d4-f07c-413e-a30c-2b48e73db32f
    Content-Type: text/html; charset=utf-8

    <p>Aut sequi illo qui vacuus. Sint bellicus blanditiis. Laboriosam congregatio ab laborum ars.</p>
    <p>Degero vigilo contra varietas qui occaecati debeo. Tempora animi appello ad est. Et ipsum desipio asper.</p>
    <p>Centum similique consequatur eos. Vitae bestia qui enim. Aedificium labore nostrum solio.</p>
    <p>Facilis ubi calculus dolorum. Et aer usus aut quod vulgo adnuo nesciunt. Thalassinus cumque voluptatem culpa.</p>
    <p>Stewart Kilback &lt;<a href="mailto:jakob@powlowskihowell.net">jakob@powlowskihowell.net</a>&gt;, Senior Marketing Architect<br>
    <b>Beer, Weissnat and Boyle</b>, <em>Team-oriented discrete initiative</em></p>
    <p><small>Generated by https://github.com/jhillyerd/fauxmailer</small></p>

    --enmime-389602d4-f07c-413e-a30c-2b48e73db32f--


## Docker

Docker Hub automated build available at
[jhillyerd/fauxmailer](https://hub.docker.com/r/jhillyerd/fauxmailer/)

- `jhillyerd/fauxmailer:stable` tracks branch `master`
- `jhillyerd/fauxmailer:latest` tracks branch `develop`

## Building from Source

You will need a functioning [Go installation][Google Go] for this to work.

Grab the fauxmailer source code and compile the executable:

    go get -v github.com/jhillyerd/fauxmailer

## About

fauxmailer is written in [Google Go]

fauxmailer is open source software released under the MIT License.  The latest
version can be found at https://github.com/jhillyerd/fauxmailer

[Google Go]:        http://golang.org/
[Inbucket]:         http://www.inbucket.org/
