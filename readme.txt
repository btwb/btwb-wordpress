=== BTWB ===
Contributors: BTWB
Donate link: https://www.beyondthewhiteboard.com/
Tags: BTWB, Access Settings, Gyms, Fitness
Requires at least: 1.0.0
Tested up to: 4.6.1
Stable tag: 1.0.0

== Description ==

A BTWB plugin which allows the Wordpress users to authenticate their website vistors with [BTWB](https://www.beyondthewhiteboard.com)

== Installation ==

Please move to your plugin's root directory. Then use composer to download and install the dependencies for this project:

```bash
composer install
```

e.g.

1. Upload the plugin files to the `/wp-content/plugins/btwb-wordpress` directory, or install the plugin through the WordPress plugins screen directly.
2. Activate the plugin through the 'Plugins' screen in WordPress
3. Click on 'BTWB' menu item at your WP Dashboard to play with settings

JSON Config

The JSON Config is the main configuration manifest for configuring
the BTWB Wordpress Plugin.

Example:

    ```
    {
      "authentication": {
        "endpoint": "https://www.beyondthewhiteboard.com/sessions/jwt/_gym_1",
        "algorithm": "RS256",
        "key": "
            -----BEGIN PUBLIC KEY-----
            MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAsY/tvf41ii7WeNY+M1Hr
            ixWE+UVQiYV1g+y2pM/6/cXYg2ZtSarzFrIj6Uq6y1etQbA7YHZoLPU5zDCIeVYc
            g7Kui2Vi3+1YpkN2knQgFcjHtYC6Y95rY6MvVgvUCugQuh+sLfAM0dk7iICoaa7s
            wVn6uvfEvZhZXCk0aPEi2I9YsHQKzdu47MKxXIB4TsDx1QzBBRJlF0M4520hCPcE
            NFQCyNKck7nshejRcXKFBObl8TINnMI+jnMHfrZeoW+wAN7jk8WRJHergemUIRWx
            j4v/kmfsHxkDft1sUdTepUNANgm+xkCsUeSEZ2JC7FZ4wJbz8rF8ChifrRg3ycUt
            UQIDAQAB
            -----END PUBLIC KEY-----
          "
      },
      "webwidgets_api_keys": {
        "acct:_api_access_key_12345@names.btwb.net": "a_crypto_bearer_token_for_gym_1"
      },
      "stripe": {
        "public_api_key": "pk_live_XXXXXX"
      },
      "member_lists": {
        "_1xxx": {
          "name": "Crossfit Kinnick (All Members)"
        },
        "_2xxx": {
          "name": "Crossfit Kinnick Coaching (All Subscribers)"
        },
        "_3xxx": {
          "name": "Crossfit Kinnick Coaching Elite Program Training (Program)"
        }
      },
      "tracks": {
        "12345": {
          "name": "Elements"
        },
        "12346": {
          "name": "Fitness"
        },
        "12347": {
          "name": "Advanced"
        }
      },
      "coaching_program_plans": {
        "-EXAMPLE_PLAN_STR_KEY_XYZABC": {
          "coaching_program_handle": "_coaching_program_1234",
          "name": "Crossfit Kinnick Coaching Elite Program Training",
          "url": "https://signup.btwb.com/programs/-EXAMPLE_PLAN_STRING_KEY_XYZABC",
          "description": "Crossfit Kinnick Coaching Elite Program Training - $45/mo",
          "amount": 4500,
          "currency": "USD"
        }
      }
    }
    ```

Example JWT Claim Signed by Wordpress to send as an API Key.

* iss - The issuer is the API Key Holder represented by the API Key Handle Email.
* aud - The audience is the btwb webwidgets service.
* exp - The expiration is the timestamp set to about 1 hour from time of creation.

    ```
    {
      "iss": "acct:_api_agent_1234@names.btwb.net",
      "aud": "acct:webwidgets@services.btwb.net",
      "exp": 1234523424
    }
    ```

== Changelog ==

= Version 2.1.20191105 =

* Fixes vendoring issue in zip release

= Version 2.1.20191029 =

* Changes JWT token expirations

= Version 2.1.20190913 =

* Fixes Font Awesome URL to https

= Version 2.1.20190505 =

= Version 2.1.20170420 =

* wod, activities and leaderboard shortcodes support Coaching Teams
* adds Coaching Program Plan signup widgets
* Updates JWT Single Sign In to support HNF public key signing.
* Uses btwb-webwigets v2.1 branch.

= Version 2.0.20170420 =

* Tag created from a typo, a match for 2.1.20170420.
* Uses btwb-webwidgets v2.0 branch.

= Version 2.0 =

* A full rewrite
* Supports protected pages via hansnfranz single sign in.

= v1.0 to v1.3: from btwb-webwidgets repository =

* Past versions, which lived in a separate repository, were a combined
  webwidgets and wordpress product.

= 1.0.0 =
* Initial Release

