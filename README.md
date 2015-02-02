# 'Refresh Template' for CodeRush #
This plugin is used to regenerate the output of templates which are themselves designed to be refreshed.

### Usage ###
Create a template with a header and footer. The header and footer should take the following form and should reference the template itself by name.

    // RefreshTemplate:MyTemplate
    <Your Normal Template Text Goes Here>
    // EndRefreshTemplate:MyTemplate

This template can be expanded as normal. however the header and footer will make it recognisable by the 'Refresh Template' Code Provider.

The '**Refresh Template**' Code Provider will make itself available via the value Code menu and will replace the previously emitted code with that specified by the Header and footer.

### Alternative Usage ###

A subtle side effect of the original design, allows for the header and footer of your template to specify a template other than the one which generates them.

This might means that if you create the following 3 templates...

**Step1**

    // RefreshTemplate:Step2
    Step1
    // EndRefreshTemplate:Step2

**Step2**

	// RefreshTemplate:Step3
	Step2
	// EndRefreshTemplate:Step3
	

**Step3**

	// RefreshTemplate:Step1
	Step3
	// EndRefreshTemplate:Step1

... you will be able to progress from **Step1** to **Step2** to **Step3** (and back to **Step1** again), simply by repeatedly invoking the **Refresh Template** Code Provider

