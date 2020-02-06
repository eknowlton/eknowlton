# In Rails 5.2, are there a need for environment variables?

I keep having small debates with coworkers about whether or not the new Rails 5.2 feature Encrypted Credentials eliminates the need to use environment variables to hold certain configuration values on the compute instance its being served from.

**Some points that have been made:**

- By eliminating the need to use environment variables to keep sensitive information from being tracked via source control enables atomic deploys
- Credentials could be broken down into environments

### VC Tracked Credentials Enables Atomic Deploys

**Point**
This is by far one of the best benefits that seems to come from encrypting credentials and storing them in version control. When a new release is deployed, it should not require any extra work to configure or add new environment variables the deployed server. In the spirit of making deploying new release as simple and efficient as possible this one is a winner.

**Counter Point**
Even though tracking credentials in source code can enable atomic deploys by reducing the work required to deploy new release with new credentials environment variables can be incorporated in to infrastructure code and be just as easily deploy-able as CI/CD. 

### Credentials Broken Down Per Environments
**Point**
One of the benefits of breaking down credentials to environments ( local, staging, production, etc ) is that not all developers will have access to different environment credentials, production is notably most relevant. This ensures that new engineers or even contractors won't have access to the most important credentials of the production system.

**Counter Point**
By keeping credentials in environment variables on the relevant server, new engineers and contractors will not have any access to these credentials either. While each environment encrypted credentials file will require a separate key, these environment variables will not require storage of any special secrets.

### Conclusion
I would love to hear what people think about rails credentials and whether or not it was a necessary or beneficial addition. I have yet to make my mind up about this, and would love to hear other points.

For example, could these two features be used side-by-side for a enhanced and easier management system?
