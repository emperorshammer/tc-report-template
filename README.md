# tc-report-template
 
This is a simple HTML template for TIE Corps unit reports.  It leverages our site's built-in CSS framework (along with a few custom classes), as well as demonstrates the use of inline CSS styles for situations where our framework does not provide the desired formatting.  The template is built to support responsiveness for mobile browsing.  Only a base level of understanding of HTML and CSS is required to use the template.

## Basic Use

The report format is based on that developed by [MAJ andr3](https://tc.emperorshammer.org/member/56112/tc) (and his predecessors) for Sin Squadron.  We have converted the template to use tags and CSS classes to make the format fit within the site's existing framework.  It is meant more as a technical implementation example than a cookie-cutter format that works perfectly for every squadron/unit.

Use the portion of report.htm between the HTML comments `BEGIN SNIP` and `END SNIP` when uploading the report to the site.  The first two lines contain code that load the CSS file from the EH site and apply a basic container for styling.  This enables you to view an *approximation* of how the report will look after uploaded to the site.  Please note that because of HTML sanitization and a couple of other factors, the end result may be *slightly* different.  Preview your report through the site to be sure before making your post.

## CSS Information

Our site uses the Bulma CSS framework.  All built-in Bulma classes are available for use in your report.  Refer to https://bulma.io/documentation/.  Note that all reports displayed on the site are automatically wrapped in a [content class](https://bulma.io/documentation/elements/content/), so that most normal HTML tags are automatically appropriately styled.

### kvRecord

The custom "kvRecord" class is applied to `<div>` to create a tabular "list" of key/value pairs, with output similar to that of a two-column table.  kvRecords resize correctly on mobile.

```
<div class="kvRecord">
    <span class="key">Name:</span>
    <span class="value">Turtle Jerrar</span>
</div>
```

## Tips/Tricks

### Tables

Use of `<table>` is discouraged, as there isn't a lot you can do to make this work well on mobile.  If you need tables, wrap the table in a `<div>` with the `table-container` class applied.  The table will still expand out of the viewport, however it will be correctly horizontally scrollable on mobile, and will not break the display of the rest of the page.

By using our CSS framework, your layout can work *with* the site instead of fighting against it.

```
<div class="table-container">
    <table>
        <!-- table content here -->
    </table>
</div>
```

### Sanitization

Our site sanitizes HTML and CSS input for safety. A few things to keep in mind:

- All `<style>` and `<link>` tags are stripped; you must use CSS using the HTML `style` **attribute** for inline CSS or HTML `class` attribute for using built-in CSS classes.
- Sizes using percentages are stripped. Styling anything using fixed width is strongly *discouraged* unless you know exactly what you're doing; fixed width items are likely to disrupt responsiveness on mobile.

For those technically inclined, the [internal whitelist definition](http://htmlpurifier.org/live/smoketests/printDefinition.php?config%5BNull_HTML.Allowed%5D=1&config%5BNull_HTML.AllowedAttributes%5D=1&config%5BHTML.AllowedComments%5D=&config%5BNull_HTML.AllowedCommentsRegexp%5D=1&config%5BNull_HTML.AllowedElements%5D=1&config%5BNull_HTML.AllowedModules%5D=1&config%5BHTML.Attr.Name.UseCDATA%5D=0&config%5BHTML.BlockWrapper%5D=p&config%5BHTML.CoreModules%5D=Structure%0D%0AText%0D%0AHypertext%0D%0AList%0D%0ANonXMLCommonAttributes%0D%0AXMLCommonAttributes%0D%0ACommonAttributes&config%5BNull_HTML.CustomDoctype%5D=1&config%5BNull_HTML.Doctype%5D=1&config%5BHTML.FlashAllowFullScreen%5D=0&config%5BHTML.ForbiddenAttributes%5D=&config%5BHTML.ForbiddenElements%5D=&config%5BHTML.MaxImgLength%5D=1200&config%5BHTML.Nofollow%5D=0&config%5BHTML.Parent%5D=div&config%5BHTML.Proprietary%5D=1&config%5BHTML.SafeEmbed%5D=0&config%5BHTML.SafeIframe%5D=0&config%5BHTML.SafeObject%5D=0&config%5BHTML.SafeScripting%5D=&config%5BHTML.Strict%5D=0&config%5BHTML.TargetBlank%5D=0&config%5BHTML.TargetNoopener%5D=1&config%5BHTML.TargetNoreferrer%5D=1&config%5BHTML.TidyAdd%5D=&config%5BHTML.TidyLevel%5D=medium&config%5BHTML.TidyRemove%5D=&config%5BHTML.Trusted%5D=0&config%5BHTML.XHTML%5D=0) is availabe.

### Mini Medal Images

A full collection of miniature medal images for reports is located at https://tc.emperorshammer.org/images/report-assets/medals/.

### Unit Patches

You can get the 'current' patch of a unit at https://tc.emperorshammer.org/patch.php?id=NUM, where *NUM* is the numerical ID of the unit.  Appending `&size=small`, `medium`, or `large` will return a resized patch at 128x128, 512x512, or 1024x1024 pixels respectively.

```
<img src="https://tc.emperorshammer.org/patch.php?id=65&size=medium">
```

### Other Image Assets

Other image assets needed for your report can be uploaded to https://tc.emperorshammer.org/view_assets.php.  Image asset uploads are intended as a permanent archival mechanism for images associated with news posts, reports, and other Emperor's Hammer records. Please do not use this area for general purpose image hosting.

## Changelog

### [1.0.0]

- Initial commit.

## Point of Contact

The point of contact for this repository is the Emperor's Hammer Internet Office at https://ehnet.org/.