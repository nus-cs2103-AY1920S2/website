We will be using a tool called [RepoSense](http://reposense.org) to make it **easier for you to see (and learn from) code written by others**, and to help us see who wrote which part of the code.

<pic src="https://github.com/reposense/RepoSense/raw/release/docs/images/report-features.png" alt="RepoSense report screenshot">
  <sub>Figure: RepoSense Report Features</sub>
</pic>

**Viewing the current status of code authorship data:**

* **The reports generated by the tool for the individual and team projects will be made available in the module website at some point in the semester. The feature that is most relevant to you is the _Code Panel_ (shown on the right side of the screenshot above). It shows the code attributed to a given author.
* Click on your name to load the code attributed to you (based on Git blame/log data) onto the code panel on the right.
* If the code shown roughly matches the code you wrote, all is fine and there is nothing for you to do.

**2. If the code does not match the actual authorship:**

* Here are the possible reasons for the code shown not to match the code you wrote:
  * the git username in some of your commits does not match your GitHub username.
  * the actual authorship does not match the authorship determined by git blame/log e.g., another student touched your code after you wrote it, and Git log attributed the code to that student instead

* In those cases, you can provide more information to RepoSense to rectify the situation, in the following way:

<div class="indented-level2">
<box>

**For simple cases** such as the following, you can create a PR to update our config files [here]({{ module_org }}/tp-dashboard/tree/master/configs). The meaning of the config files are given in the [RepoSense user guide](https://github.com/reposense/RepoSense/blob/release/docs/UserGuide.md#customize-using-csv-config-files).
  * missing some commits due to using multiple git `user.name`s
  * some commits/files need to be omitted from the analysis

For more complicated needs, follow the instructions below this box. If you are not sure which option to use, please post in the [forum]({{ forum_link }}) to ask.
</box>
</div>

  * Install RepoSense (see the [Getting Started](https://github.com/reposense/RepoSense/blob/release/docs/UserGuide.md#getting-started) section of the RepoSense User Guide)
  * Use the two methods described in the RepoSense User Guide section [Configuring a Repo to Provide Additional Data to RepoSense](https://github.com/reposense/RepoSense/blob/release/docs/UserGuide.md#configuring-a-repo-to-provide-additional-data-to-reposense) to provide additional data to the authorship analysis to make it more accurate.
   * If you add a `config.json` file to your repo (as specified by one of the two methods),
     * **Please use the exact partial name from [here]({{ team_IDs_page }})** as the display name.<br>
       e.g., `"displayName": "ABDUL ... JAVID",`
     * If your commits have multiple author names, specify all of them<br>
       e.g., `"authorNames": ["theMyth", "theLegend", "The Gary"]`
     * Update the line `config.json` in the `.gitignore` file of your repo as `/config.json` so that it ignores the `config.json` produced by the app but not the `_reposense/config.json`.
   * If you add `@@author` annotations, please follow the guidelines below:

<div class="indented-level2">
<panel header="Adding `@@author` tags to indicate authorship">
  <include src="reposenseAuthorAnnotation.md" />
</panel>
</div>

  * After you are satisfied with the new results (i.e., results produced by running RepoSense locally), push the `config.json` file you added and/or the annotated code to your repo. We'll use that information the next time we run RepoSense (we run it at least once a week).
  * If you choose to annotate code, minimize annotating code chunks smaller than a method. We do not grade code snippets too small to be read meaningfully.
  * If you encounter any problem when doing the above or if you have questions, please post in the [forum]({{ forum_link }}).

==**We recommend you ensure your code is RepoSense-compatible by v1.3**==
