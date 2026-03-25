# How to add new variables?
## Course Wide - From CMS
Settings -> Advanced -> Certificate Web View Overrides. There just create a json like:
```
{
	"custom_key" : "custom_val"
}
```
## Platform Wide - From Django Admin Panel
Certificates -> Certificate html web view configurations. Add a json and keys inside of a default key like:
```
{ 
	"default": 
	{ 
		"custom_key" : "custom_val"
	}
}
```

# List of variables loaded into the context by ~/edx-platform/lms/djangoapps/certificates/views/webview.py context functions

### 1. Basic Platform & UI Variables
*Source: `_update_context_with_basic_info`*

| Variable | Description |
| :--- | :--- |
| `platform_name` | The name of the platform as defined in site settings. |
| `course_id` | The unique course run identifier string. |
| `copyright_text` | Auto-generated copyright notice including the current year. |
| `logo_subtitle` | Subtitle appearing under the logo (Default: "Certificate Validation"). |
| `document_banner` | Header text acknowledging the student's accomplishment. |
| `certificate_date_issued_title` | Label for the issuance date field. |
| `certificate_id_number_title` | Label for the unique certificate ID field. |
| `certificate_info_title` | Title for the section describing platform certificates. |
| `certificate_verify_title` | Title for the certificate validation instructions. |
| `certificate_verify_description` | Text explaining the GPG/digital signature validation process. |
| `certificate_verify_urltext` | Link text for the independent validation action. |
| `accomplishment_copy_about` | Label for the "About Accomplishments" informational section. |
| `company_tos_urltext` | Link text for Terms of Service and Honor Code. |
| `company_privacy_urltext` | Link text for the Privacy Policy. |
| `company_about_title` | Heading for the "About the Organization" section. |
| `company_about_description` | Brief description of the organization's mission. |
| `company_about_urltext` | Link text for the organization's "Learn More" page. |
| `company_courselist_urltext` | Link text for the platform course catalog. |
| `company_careers_urltext` | Link text for the organization's careers page. |
| `company_contact_urltext` | Link text for the contact/support page. |

### 2. Organization Variables
*Source: `_update_organization_context`*

| Variable | Description |
| :--- | :--- |
| `organization_long_name` | The full legal name of the organization offering the course. |
| `organization_short_name` | The abbreviated name or acronym of the organization. |
| `accomplishment_copy_course_org` | Organizational identifier used in achievement descriptions. |
| `organization_logo` | URL to the specific branding logo for the course organization. |

### 3. Course Variables
*Source: `_update_course_context`*

| Variable | Description |
| :--- | :--- |
| `accomplishment_copy_course_name` | The official course title used for certificate display. |
| `course_number` | The public-facing course number (e.g., CS101). |
| `full_course_image_url` | Absolute URL to the course promotional/about image. |
| `idv_enabled_for_certificates` | Boolean indicating if ID verification is a requirement for this cert. |
| `accomplishment_copy_course_description` | Standardized text describing the course as an offering of the partner. |

### 4. User/Learner Variables
*Source: `_update_context_with_user_info`*

| Variable | Description |
| :--- | :--- |
| `username` | The internal system username of the certificate recipient. |
| `accomplishment_copy_username` | The learner's username as displayed on the certificate page. |
| `accomplishment_user_id` | The unique database primary key for the user. |
| `accomplishment_copy_name` | The preferred full name of the learner for certificate rendering. |
| `course_mode` | The enrollment track type (e.g., verified, honor, professional). |
| `accomplishment_banner_opening` | Congratulatory headline addressing the learner by name. |
| `accomplishment_banner_congrats` | Instructional text regarding sharing the achievement. |
| `accomplishment_more_title` | Heading for additional learner-specific accomplishment data. |
| `accomplishment_copy_more_about` | Link text for finding more details on the learner's achievement. |
| `user_language` | The locale/language code currently used for rendering. |

### 5. Certificate Achievement Variables
*Source: `_update_certificate_context`*

| Variable | Description |
| :--- | :--- |
| `certificate_id_number` | The unique verification UUID for the specific certificate. |
| `certificate_verify_url` | The absolute URL used by third parties to verify the certificate. |
| `certificate_date_issued` | The localized date on which the certificate was officially issued. |
| `certificate_type_description` | Detailed text explaining the requirements of the specific cert type. |
| `certificate_info_description` | General text acknowledging platform-wide achievement standards. |
| `document_title` | The string used for the HTML `<title>` tag in the browser. |
| `document_meta_description` | SEO metadata describing the validity of the specific user's cert. |
| `accomplishment_copy_description_full` | Narrative text confirming the user's passing grade and award. |

### 6. Social Sharing Variables
*Source: `_update_social_context`*

| Variable | Description |
| :--- | :--- |
| `share_url` | The canonical URL used for social media sharing and indexing. |
| `facebook_share_enabled` | Boolean flag indicating if Facebook sharing is active. |
| `facebook_app_id` | The unique ID for the platform's Facebook integration. |
| `facebook_share_text` | Pre-populated text for a learner's Facebook post. |
| `twitter_share_enabled` | Boolean flag indicating if Twitter sharing is active. |
| `twitter_url` | The pre-formatted Twitter intent URL for "one-click" tweeting. |
| `twitter_share_text` | Pre-populated content for the learner's tweet. |
| `linked_in_url` | The pre-formatted URL to add the certificate to a LinkedIn profile. |
