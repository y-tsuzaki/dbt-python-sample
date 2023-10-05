# dbt-falでpython実行するテスト

```profiles.yml
dbt_python_sample:
  outputs:
    dev_with_fal:
      type: fal
      db_profile: dev_bigquery
    dev_bigquery:
      dataset: dbt_python_sample
      job_execution_timeout_seconds: 300
      job_retries: 1
      location: asia-northeast1
      method: oauth
      priority: interactive
      project: ytsuzaki-dbt-sample
      threads: 1
      type: bigquery
  target: dev_with_fal
```

以下の設定を追加した。
元々のtarget名はdevだったが区別のためdev_bigqueryとした。
```
    dev_with_fal:
      type: fal
      db_profile: dev_bigquery
```

targetを`dev_with_fal`に設定する。
設定しないと`dbt run`時に以下のエラーが発生する。
```
 Need to supply dataproc_region in profile to submit python job
```

![スクリーンショット 2023-10-06 0 43 08](https://github.com/y-tsuzaki/dbt-python-sample/assets/26266190/7d3990f8-abeb-4e33-9fb0-b425258f38d2)

--- 
Welcome to your new dbt project!

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
