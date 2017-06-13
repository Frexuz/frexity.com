# Rails guidelines

Specific guidelines for how we code Rails.

## Queries

Always use query classes. These classes should only have a `results` method, and only use `ActiveRecord` to query data. No other business logic unless really necessary.

```
# Bad
def index
  @department_employees = Employee.where(company_id: 1, department_id: 4).pluck(:name).order(:name)
end

# Good
def index
  @department_employees = DepartmentsIndexQuery.new.results(@company.employees)
end

class EmployeeIndexQuery

  def results(scope = Employee.all)
    scope
      .where(department_id: 4)
      .pluck(:name)
      .order(name: :asc)
  end

end
```
