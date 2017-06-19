# Rails guidelines

Specific guidelines for how we code Rails.

## List of stuff you should know as your second language :D

- Inflections: http://api.rubyonrails.org/classes/ActiveSupport/Inflector.html

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

Exception: For `.find` queries, use this pattern:

```
# Bad
def update
  @department = DepartmentIdQuery.new.results(params[:department_id])
  @department.save
end

# Good
def update
  department.assign_attributes(department_params)
end

private

def department
  @department ||= Department.find(params[:id])
end
```

Always use scoped queries for relations

```
# Bad
@department = Department.find(params[:id])

# Good
@department = current_company.departments.find(params[:id])
```
