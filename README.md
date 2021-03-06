# Fresh Smiles

An application using the Freshdesk Survey API and a PHP/MySQL backend for storing and displaying survey data. Also includes a complete template and functions to display the results on a pretty page. Inspired by [Smiley from 37 Signals](http://smiley.37signals.com).

## Requirements
1. PHP
2. MySQL
3. Cron
4. Curl for PHP

## Installation
1. Setup a MySQL Table using /scrips/schema.sql
2. Copy /inc/config-sample.php to /inc/config.php (local or private deployment)
3. Copy /inc/smiley-config-sample.php to /inc/smiley-config.php (local or private deployment)
4. Setup /scripts/cron.php to run via cronjob (1 hour or more)
5. You can use webhooks and observer rules instead of cron jobs
    - Create an Observer rule with this config:
      - Event: Customer Feedback is Received, Rating: Any
      - performed by: Any
      - Actions: Trigger Webhook ->
        - Callback URL: http://{{smiles.yourcompany.com}}/scripts/hook.php
        - Encoding: X-FORM-URLENCODED
        - Content: Simple, select just the Ticket ID.
        - Save the Rule.

## Deployment
1. Setup Project with DeployHQ
2. Setup config files in DeployHQ (config.php & smiley-config.php)
3. Deploy Project
4. Profit

## Modules
Built with:
  - [FreshDesk Rest](https://github.com/phikai/freshdesk-rest) by [phikai](https://github.com/phikai) (Forked from [blak3r](https://github.com/blak3r/freshdesk-solutions))
  - [Fresh-smiles from zippykid](https://github.com/zippykid/fresh-smiles) 
## License
Licensed under the MIT Licnese, see [LICENSE](license)

## Contributing
If you'd like to contribute to the project feel free to submit issues or pull requests to the project.

## Example
[Freshdesk Customer Happiness Report](http://smiles.freshdesk.com)
