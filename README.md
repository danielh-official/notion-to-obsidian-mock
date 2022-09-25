# Notion to Obsidian Mock

A mock to visually explain how the "Notion to Obsidian" plugin should behave.

- [Notion Workspace](https://www.notion.so/Home-838387094c0849639171f439169656dd)

## How to Use This

- The purpose of this repo is to demonstrate how the Notion to Obsidian plugin should work.
- The way that pages look (e.g., Home) should reflect on [Vault](/Vault).

## Outline

- One-way sync from Notion to Obsidian
- Creates a folder (e.g., "Notion") in Obsidian vault where all Notion pages are stored with their unique ids as their file names.
- 7 default fields
	- **from**: a string denoting the block type that the block page is a member of
	  - **database**: the block is a member of a database
	  - **page**: the block is a subpage
	- **database**: a boolean that tells you whether the page is a database or not
	- **title**: the display title of the block
	- **id**: the unique immutable id of the block
	- **created_at**: the date the block was created
	- **updated_at**: the date the block was recently updated
	- **created_by**: the user who created the block
	- **updated_by**: the user who recently updated the block
- Custom fields are added if “from” is set to “database” and there are any custom fields.
- Relations are stored as inline key/value pairs.
	- e.g., “Relation:: Test”

## Folders

- **Dates**: the folder where all date markdown files are stored. The alias that's used for the date file is based on relative time.
- **Users**: the folder where all user markdown files are stored. Used for "assignee" data types.
- **Pages**: the meat of the plugin. All pages are stored here as uniquely named markdown files. The plugin will try to make the pages mirror their Notion versions as much as possible.

## Settings

- **Folder**: The folder that’s used to store all Notion pages.
	- Default: “Notion”
	- Will show warning if there is a folder of the same name with populated items and prevent the plugin from running
- **Don’t create Dates folder**: This option will keep the plugin from creating a Dates folder in the Notion folder
	- Useful if you want to keep dates centered in one area
- **Don't create Users folder**: Like the "Don't create Dates folder" option, this prevents automatic creation of a user file
  - Useful if you want to use the markdown files located natively in your Obsidian vault 
