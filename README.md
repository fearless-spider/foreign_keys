# Multi-tenancy with foreign keys

Pros

    data isolation - foreign keys ensure that each record is associated with a specific tenant, preventing data leakage between tenants. This isolation makes the data store more secure and reliable,
    simplifies queries - filtering records by tenant_id becomes straightforward, making it easy to retrieve information specific to a tenant,
    ease of implementation - adding a tenant_id to tables and establishing foreign key relationships is a relatively simple and well-understood approach. Configuring the database schema this way ensures that each tenant's data is properly stored and managed,
    performance - thanks to having tenant_id in each table, we can omit multiple join statements, which can lead to query speed-up.

Cons

    redundancy - including tenant_id in many tables can lead to huge redundancy, which might require additional storage space,
    the potential of data inconsistencies - if not carefully managed, there is a risk of data inconsistencies (orphaned records, mismatched tenant IDs, missing foreign keys constraints, or inconsistent deletions),
    scalability - as the number of tenants grows, tables can become very large, which might impact performance (hence, solutions such as partitioning or sharding might be needed)

To start your Phoenix server:

- Run `mix setup` to install and setup dependencies
- Start Phoenix endpoint with `mix phx.server` or inside IEx with `iex -S mix phx.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](https://hexdocs.pm/phoenix/deployment.html).

## Learn more

- Official website: https://www.phoenixframework.org/
- Guides: https://hexdocs.pm/phoenix/overview.html
- Docs: https://hexdocs.pm/phoenix
- Forum: https://elixirforum.com/c/phoenix-forum
- Source: https://github.com/phoenixframework/phoenix
