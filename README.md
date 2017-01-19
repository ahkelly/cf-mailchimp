#CF MailChimp
ColdFusion wrapper for the MailChimp 3.0 API

##Work in Progress
This wrapper is a work in progress. I have prioritized building out the features needed for my projects. 
If there is a feature that you would like added, please [open an issue](https://github.com/kevindb/cf-mailchimp/issues/new) or [submit a pull request](https://github.com/kevindb/cf-mailchimp/pulls).

##List of available methods
- getLists - Retrieves all lists in the account
- getList - Retrieves information about the specified list
- getListMembers - Retrieves a list of all members of the specified list
- getListMember - Retrieves details on a single member of the specified list
- putListMembers - Uses a batch operation to add or update multiple members of the specified list
- putListMember - Adds or updates a single member to the specified list

##Requirements
I have only tested on Adobe ColdFusion 11. I am confident that the wrapper will work in Lucee/Railo 4. It may work in ACF 10 and will NOT work in ACF 9-.

##Usage
```
mc = new mailchimp(
	apiKey = "YOURAPIKEY",	// see http://kb.mailchimp.com/accounts/management/about-api-keys
	apiHost = "https://us1.api.mailchimp.com/3.0/",
	debug = true			// note debug setting
);

lists = mc.getLists();

newMember = mc.putListMember(
	listId = "YOURLISTID",	// see http://kb.mailchimp.com/lists/managing-subscribers/find-your-list-id
	data = {
		"email_address" = "hey@example.com",
		"status" = "subscribed",
		"merge_fields" = {
			"FNAME" = "Hey",
			"Now" = "Finley",
			"COMPANY" = "Acme"
		}
	}
);
```

##Resources
[MailChimp API 3.0 Documention](http://developer.mailchimp.com/)

##Contributors
This project is based on previous work by others. 
See [CONTRIBUTORS](CONTRIBUTORS.md) for details.

##License

This repository is licensed under the GNU Lesser General Public License v2.1. 
See [LICENSE](LICENSE) for details.
