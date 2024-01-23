### Exposing a v2 for certain models

#### Goal

#### Phase 1
* Let's call existing models as "v1" models.
* If an existing model is undergoing a breaking change, we'd need a v2 of the same.
* Consumers of our models who need 
the newer version need to explicitly opt in 
to v2 models.

#### Phase 2
* After a period of time, "v2" would be the default, that is, opting in would no longer 
be necessary. 
* Consumers who wish to continue using the older
models need to opt-out of v2 by explicitly opting in to use v1.


### How

#### Phase 1

* Define the model in <existing_model>_v2.sql
* Update schema.yaml to point to have "v: 1" alias'd to the existing name of the table/view.
* For "v1", explicitly specify the name of the SQL file where the model is defined in. Otherwise, DBT would look for one with a suffi _v1.
* For "v1", explicitly pin the name of the table to the existing one, else DBT would create a new one with the suffix "_v1"

#### Phase 2

* 



### Using the starter project

Try running the following commands:
- dbt run
- dbt test


### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices
