# ActiveCampaignV3Api

This gem is created as a wrapper in order to utilize the latest features from ActiveCampaign's v3 API. Refer to https://developers.activecampaign.com/reference for documentation.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'active_campaign_v3_api'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install active_campaign_v3_api

## TODOs

Note: this gem is still under heavy development. The following is the current progress of development

- ADDRESSES
  + [ ] Addresses
- AUTOMATIONS
  + [ ] Automations
- BRANDING
  + [ ] Branding
- CALENDAR FEEDS
  + [ ] Calendar Feeds
- CAMPAIGNS
  + [ ] Campaigns
  + [ ] Messages
- CONTACTS
  + [ ] Contacts
  + [ ] Automations
  + [ ] Customs Fields
  + [ ] Custom Field Values
  + [ ] Tags
- DEALS
  + [ ] Deals
  + [ ] Pipelines
  + [ ] Stages
  + [ ] Custom Deal Fields
  + [ ] Custom Deal Fields Values
  + [ ] Secondary Contract
- DEEP DATA INTEGRATIONS
  - [ ] Connections
  - [ ] E-Commerce Abandoned Carts
  - [ ] E-Commerce Customers
  - [ ] E-Commerce Orders
- FORMS
  - [ ] Forms
- LISTS
  - [ ] Lists
- NOTES
  - [ ] Notes
- ORGANIZATIONS
  - [ ] Organizations
- SAVED RESPONSES
  - [ ] Saved Responses
- SCORES
  - [ ] Scores
- SEGMENTS
  - [ ] Segments
- SETTINGS
  - [ ] Settings
- SITE & EVENT TRACKING
  - [ ] Event Tracking
  - [ ] Site Tracking
- TAGS
  - [ ] Tags
- TASKS
  - [ ] Tasks
- TASK TYPES
  - [ ] Task Types
- TEMPLATES
  - [ ] Templates
- USERS
  - [ ] Users
  - [x] Groups
- WEBHOOKS
  - [ ] Webhooks

## Usage

Instantiate the client by the following
```
client = ActiveCampaignV3Api::Client.new(api_token: <YOUR_API_TOKEN>, account_id: <YOUR_ACCOUNT_ID>
```

Your account ID is the ID that was associated with your account.

While your API Token can be found under `Settings` > `Developer` (Alternatively you can visit https://<YOUR_ACCOUNT_ID>.activehosted.com/app/settings/developer)

After that, refer to the documentations for the method's name. For example, if you want to create a group. Refer to the document here: https://developers.activecampaign.com/reference#groups . The method name is take from the endpoint's title and converted into snakecase (e.g. "Create a group" -> "create_a_group")

Therefore you can call the method by

```
client.create_a_group(data)
```

The number of arguments needed for each method will be dependent on the endpoint that was being called.

1. If the endpoint does not require id and data, then there will be no argument
Example: https://developers.activecampaign.com/reference#list-all-groups

```
client.list_all_groups
```

2. If the endpoint require only id, then there will be 1 argument

```
id = 1
client.retrieve_a_group(id)
```

3. If the endpoint require only data, then there will be 1 argument

```
data = { group: { title: 'Testing' } }
client.retrieve_a_group(data)
```

4. If the endpoint require both id and data, then there will be 2 arguments. Id will be the first followed by Data

```
id = 1
data = { group: { title: 'Testing' } }
client.update_a_group(id, data)
```

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/active_campaign_v3_api. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the ActiveCampaignV3Api project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/[USERNAME]/active_campaign_v3_api/blob/master/CODE_OF_CONDUCT.md).
