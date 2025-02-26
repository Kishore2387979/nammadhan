# nammadhan


<!-- Implement code here -->
@model LibraryManagementSystem.Models.BranchDetails
 
@{
    ViewData["Title"] = "Index";
}
 
<h2>Index</h2>
 
<p>
<a id="lnkCrBranch" asp-controller="Library" asp-action="Create">Create Branch</a>
</p>
<p>
<a id="lnkGetBranch" asp-controller="Library" asp-action="GetBranchDetails">Get Branch Details</a>
</p>
<p>
<a id="lnkCrBook" asp-controller="Library" asp-action="CreateBooksDetails">Create Book Details</a>
</p>
<p>
<a id="lnkGetBook" asp-controller="Library" asp-action="GetBookDetails">Get Book Details</a>
</p>
<p>
<a id="lnkCrLibrarian" asp-controller="Library" asp-action="CreateLibrarian">Create Librarian</a>
</p>
<p>
<a id="lnkGetLibrarian" asp-controller="Library" asp-action="GetLibrarianDetails">Get Librarian Details</a>
</p>
<p>
<a id="lnkCrMember" asp-controller="Library" asp-action="CreateMembership">Create Membership</a>
</p>
<p>
<a id="lnkGetMember" asp-controller="Library" asp-action="GetMembershipDetails">Get Membership Details</a>
</p>


@model IEnumerable<Members>
@{
    ViewBag.Title = "Membership Details";
}
<h2>Membership Details</h2>
<table class="table" id="getMembers">
<thead>
<tr>
<th>Name</th>
<th>Gender</th>
<th>Contact</th>
<th>Branch</th>
</tr>
</thead>
<tbody>
        @foreach (var item in Model)
        {
<tr>
<td>@item.Name</td>
<td>@item.Gender</td>
<td>@item.Contact</td>
<td>@item.Branch?.BranchName</td>
</tr>
        }
</tbody>
</table>   
gt

@model Members
@{
 
    ViewBag.Title = "Create Membership";
 
}
<h2>Create Membership</h2>
<form asp-action="CreateMembership" method="post">
<div class="form-group">
<label asp-for="Name" class="control-label"></label>
<input asp-for="Name" class="form-control" />
<span asp-validation-for="Name" class="text-danger"></span>
</div>
<div class="form-group">
<label asp-for="Gender" class="control-label"></label>
<input asp-for="Gender" class="form-control" />
<span asp-validation-for="Gender" class="text-danger"></span>
</div>
<div class="form-group">
<label asp-for="Contact" class="control-label"></label>
<input asp-for="Contact" class="form-control" />
<span asp-validation-for="Contact" class="text-danger"></span>
</div>
<div class="form-group">
<label asp-for="BranchId" class="control-label"></label>
<select asp-for="BranchId" class="form-control" asp-items="ViewBag.Branches"></select>
<span asp-validation-for="BranchId" class="text-danger"></span>
</div>
<div class="form-group">
<input type="submit" value="Create" class="btn btn-primary" id="MemberCreationBtn" />
</div>
</form>
@if (ViewBag.Message != null)
 
{
<h2 id="Message">@ViewBag.Message</h2>
 
}
