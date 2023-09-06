# DriveWorks Example: Styling with `ProjectStyles.css`

### Version: 1.0.0

#### Minimum DriveWorks Version: 21.0

> For styling via CSS in DriveWorks 20.3 and below, see: [Integration Theme Example - Styling with External CSS](https://github.com/DriveWorks/IntegrationThemeExample-StylingWithExternalCSS)

A distributable example that demonstrates how to style DriveWorks Controls using CSS via `ProjectStyles.css`.

`ProjectStyles.css` is the optional custom stylesheet automatically loaded in DriveWorks desktop applications and Live when placed next to a `.driveprojx` file.

---

Please note: DriveWorks are not accepting pull requests for this example.  
Join our [online community](https://my.driveworks.co.uk) for discussion, resources and to suggest other examples.

---

### This example:
- Provides a DriveWorks Package (`.drivepkg`) containing an example Project that demonstrates using `ProjectStyles.css` and the "Metadata" Property.
- Demonstrates:
    - Using `ProjectStyles.css` to apply additional styling in Desktop and Live Forms.
    - Using CSS Attribute Selectors
        - https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors
    - Targeting Controls with the "Metadata" property (`data-metadata`)
    - Using the `::part()` Selector
    - State-based styles (`:hover`, `:focus`, `:active`)
    - Rounded Corners (`border-radius`)
    - Shadows (`box-shadow`)
    - Animating styles (`transition`)
    - CSS Transforms (`rotate`, `scale`, `skew`)
    - CSS Filters (`blur`, `grayscale`)
    - Gradients (`linear-gradient`)

The CSS selectors/styles demonstrated can be viewed without extracting the provided Project, for quick reference.
Simply open the included `ProjectStyles.css` file.

### To use this Project:
1. Clone this repository, or download as a `.zip`.

2. Extract the supplied `.drivepkg` file using the DriveWorks Content Installer to access the included Project file.
    * Ensure the included `ProjectStyles.css` file remains alongside the included `.driveprojx` Project file.

3. Open the extracted Group in DriveWorks Administrator and use 'Form Design' to view each Controls and its Properties.
    * Most importantly: the "Metadata" properties that are targeted via CSS.

### To view this Project in a browser:

1. In `DriveWorksLiveConfigUser.xml`, add a new Group Alias for the Group containing the example Project.
    * See [Integration Theme Settings](https://docs.driveworkspro.com/Topic/IntegrationThemeSettings) for additional guidance.

2. Open the extracted Group in DriveWorks Live and start the Integration Theme.
    * See [Selecting the Integration Theme](https://docs.driveworkspro.com/Topic/IntegrationThemeSelect) for additional guidance.

3. Enter your Integration Theme details into `config.js` for the example.
    * `serverUrl` - The URL that hosts your Integration Theme, including any ports.
    * `groupAlias` - The public alias created for the Group containing the DriveApps to render - as configured in `DriveWorksConfigUser.xml`.
        * This *must* be specified for each Group you wish to use.
        * This allows you to mask the true Group name publicly, if desired.
        * See [Integration Theme Settings](https://docs.driveworkspro.com/Topic/IntegrationThemeSettings) for additional guidance.
    * `projectName` - The name of the Project to render a Specification from.
        * These are pre-filled with supplied Project's name, but can be changed if required.

4. Ensure that the Integration Theme server is running, using any of the available methods (e.g. Personal Web Edition, DriveWorks Live, IIS)
    * For more information, see [Selecting the Integration Theme](https://docs.driveworkspro.com/Topic/IntegrationThemeSelect).

5. Open the example HTML files locally (localhost) or on a remote server.
    * Ensure `<corsOrigins>` in `DriveWorksConfigUser.xml` permits request from this location.
    See [Integration Theme Settings](https://docs.driveworkspro.com/Topic/IntegrationThemeSettings) for additional guidance.

6. If encountering any issues, check the browser's console for error messages (F12)

### Potential Issues:
* When serving this example for a domain different to your DriveWorks Live server, e.g. api.my-site.com from company.com, 'SameSite' cookie warnings may be thrown when the Client SDK attempts to store the current session id.
    * This appears as "Error: 401 Unauthorized" in the browser console, even with the correct configuration set. 
    * To resolve:
        * Ensure you are running a DriveWorks version compatible with this example (21.0 or above), HTTPS is enabled in DriveWorks Live's settings and a valid SSL certificate has been configured via `DriveWorksConfigUser.xml`.
        * See [Integration Theme Settings](https://docs.driveworkspro.com/Topic/IntegrationThemeSettings) for additional guidance.
* If serving your site over HTTPS, you may encounter issues with the `ProjectStyles.css` hashed resource URL not loading as it is blocked by the browser.
    * This appears as "Error: Mixed Content" in the browser console.
    * To resolve:
        * Try setting `httpsForceSslOnResources` to `True` in `DriveWorksConfigUser.xml`.
        * See [Integration Theme Settings - httpsForceSslOnResources](https://docs.driveworkspro.com/topic/IntegrationThemeSettings#httpsForceSslOnResources) for additional guidance.

---

This source code has been made available to demonstrate how you can integrate with DriveWorks using the DriveWorks Live API.
This code is provided under the MIT license. For more details, see the included LICENSE file.

The example requires that you have the latest DriveWorks Live SDK installed, operational and remotely accessible.
